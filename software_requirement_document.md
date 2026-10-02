# Software Requirement Document

# Task Tracker REST API

## Project Overview

Task Tracker API is a B2B REST API for managing authenticated user tasks. It supports registration, login, task creation, task retrieval, and status management with `OPEN`, `IN_PROGRESS`, and `COMPLETED`.

## User Stories

### User Signup

As a B2B user, I want to register with name, email, and password so that I can securely access the API.

**Acceptance criteria:** Name, email, and password are required; email is unique; the password is hashed; successful signup returns HTTP 201; invalid input returns HTTP 400; duplicate email returns HTTP 409.

### Task Creation

As an authenticated user, I want to create tasks so that I can track work.

**Acceptance criteria:** A bearer token is required; title is mandatory; status defaults to `OPEN`; only approved statuses are allowed; successful creation returns HTTP 201.

### Task Updates

As a task owner, I want to update task fields and status so that work progress is accurate.

**Acceptance criteria:** A bearer token is required; only the owner can update; invalid statuses return HTTP 400; missing or unauthorized tasks return HTTP 404.

## SQL Scripts

```sql
CREATE TABLE users (
  id BIGSERIAL PRIMARY KEY,
  name VARCHAR(120) NOT NULL,
  email VARCHAR(255) NOT NULL UNIQUE,
  password_hash TEXT NOT NULL,
  created_at TIMESTAMPTZ NOT NULL DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE tasks (
  id BIGSERIAL PRIMARY KEY,
  user_id BIGINT NOT NULL,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  status VARCHAR(20) NOT NULL DEFAULT 'OPEN',
  due_date DATE,
  created_at TIMESTAMPTZ NOT NULL DEFAULT CURRENT_TIMESTAMP,
  CONSTRAINT fk_tasks_user FOREIGN KEY (user_id)
    REFERENCES users(id) ON DELETE CASCADE,
  CONSTRAINT chk_tasks_status CHECK (status IN ('OPEN', 'IN_PROGRESS', 'COMPLETED'))
);

CREATE INDEX idx_tasks_user_id ON tasks(user_id);
CREATE INDEX idx_tasks_status ON tasks(status);
```

## Final Code Controllers

### `taskController.js`

```javascript
const db = require("./db");

const ALLOWED_STATUSES = new Set(["OPEN", "IN_PROGRESS", "COMPLETED"]);

function normalizeTaskInput(body) {
  const title = typeof body.title === "string" ? body.title.trim() : "";
  const description = typeof body.description === "string" ? body.description.trim() : null;
  const status = body.status || "OPEN";
  const dueDate = body.due_date || null;

  if (!title) return { error: "title is required." };
  if (!ALLOWED_STATUSES.has(status)) {
    return { error: "status must be OPEN, IN_PROGRESS, or COMPLETED." };
  }

  return { title, description, status, dueDate };
}

async function createTask(req, res) {
  const input = normalizeTaskInput(req.body);
  if (input.error) return res.status(400).json({ error: input.error });

  try {
    const result = await db.query(
      `INSERT INTO tasks (user_id, title, description, status, due_date)
       VALUES ($1, $2, $3, $4, $5)
       RETURNING id, user_id, title, description, status, due_date, created_at`,
      [req.user.id, input.title, input.description, input.status, input.dueDate]
    );
    return res.status(201).json({ data: result.rows[0] });
  } catch (error) {
    console.error("Task creation failed:", error);
    return res.status(500).json({ error: "Unable to create task." });
  }
}

async function getTaskById(req, res) {
  const taskId = Number.parseInt(req.params.id, 10);
  if (!Number.isSafeInteger(taskId) || taskId < 1) {
    return res.status(400).json({ error: "Task ID must be a positive integer." });
  }

  try {
    const result = await db.query(
      `SELECT id, user_id, title, description, status, due_date, created_at
       FROM tasks WHERE id = $1 AND user_id = $2`,
      [taskId, req.user.id]
    );
    if (result.rowCount === 0) return res.status(404).json({ error: "Task not found." });
    return res.status(200).json({ data: result.rows[0] });
  } catch (error) {
    console.error("Task lookup failed:", error);
    return res.status(500).json({ error: "Unable to retrieve task." });
  }
}

module.exports = { createTask, getTaskById };
```

### `authController.js`

```javascript
const bcrypt = require("bcrypt");
const db = require("./db");

async function login(req, res) {
  const { email, password } = req.body;
  if (typeof email !== "string" || typeof password !== "string") {
    return res.status(400).json({ error: "email and password are required." });
  }

  try {
    const result = await db.query(
      "SELECT id, name, email, password_hash FROM users WHERE email = $1",
      [email.trim().toLowerCase()]
    );
    const user = result.rows[0];
    if (!user || !(await bcrypt.compare(password, user.password_hash))) {
      return res.status(401).json({ error: "Invalid email or password." });
    }
    return res.status(200).json({
      message: "Login successful.",
      user: { id: user.id, name: user.name, email: user.email }
    });
  } catch (error) {
    console.error("Login failed:", error);
    return res.status(500).json({ error: "Unable to process login." });
  }
}

module.exports = { login };
```
