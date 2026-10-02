# Prompt Library — Task Tracker API

## Least-to-Most Requirements Prompt

```text
Act as a Business Analyst. We want to design a backend REST API named "{{API_NAME}}" for B2B organizations.

First, outline the system architecture scope. Then write {{USER_STORY_COUNT}} core B2B user stories for User Signup, Task Creation, and Task Updates. Include acceptance criteria and relevant HTTP status codes.

Allowed task statuses: {{ALLOWED_STATUSES}}.

Do not write database schemas or backend code yet.
```

## SQL Database Schema Prompt

```text
Act as a Database Architect. Generate raw PostgreSQL DDL SQL for "{{API_NAME}}".

Create users(id, name, email, password_hash, created_at) and tasks(id, user_id, title, description, status, due_date, created_at).

Use PRIMARY KEY, NOT NULL, UNIQUE, and FOREIGN KEY constraints. Make users.email UNIQUE. Reference tasks.user_id to users.id with ON DELETE CASCADE. Restrict task status to {{ALLOWED_STATUSES}}. Include indexes. Output SQL only. Do not use an ORM.
```

## CRISPE Controller Prompt

```text
Capacity: Act as a Senior Backend Software Engineer experienced in {{LANGUAGE}}, {{FRAMEWORK}}, PostgreSQL, REST APIs, and secure coding.

Recipient: Development team building {{API_NAME}}.

Instruction: Create controllers for POST {{API_BASE_PATH}}/tasks and GET {{API_BASE_PATH}}/tasks/:id. Use raw SQL through {{DATABASE_DRIVER}} only, with no ORM. Authenticate using {{AUTH_USER_FIELD}}. Validate title and statuses. Return 201 after creation, 400 for invalid input, and 404 for a missing or unauthorized task.

Style: Use async/await, DRY/SOLID principles, inline comments, JSON errors, and try/catch blocks.

Parameters: Allowed statuses are {{ALLOWED_STATUSES}}. Default status is {{DEFAULT_STATUS}}.

Evaluation: All SQL must use positional parameters like {{SQL_PLACEHOLDER_STYLE}}. Never concatenate request data into SQL.
```

## Secure Reflection Prompt

```text
Act as a Security Auditor. Scan the code block below for security vulnerabilities, including SQL injection, plain-text password handling, missing validation, authorization gaps, information leakage, and unhandled crashes.

For each issue, identify it, explain its risk, and write a secure refactored version.

Use {{DATABASE_DRIVER}} parameterized SQL with placeholders such as {{SQL_PLACEHOLDER_STYLE}}, try/catch blocks, validation, and {{PASSWORD_LIBRARY}} password comparison where login is involved. Do not use an ORM.

Code to audit:
```{{LANGUAGE}}
{{CODE_BLOCK}}
```
```

## Variables

| Variable | Example |
|---|---|
| `{{API_NAME}}` | Task Tracker API |
| `{{USER_STORY_COUNT}}` | 3 |
| `{{ALLOWED_STATUSES}}` | OPEN, IN_PROGRESS, COMPLETED |
| `{{LANGUAGE}}` | JavaScript |
| `{{FRAMEWORK}}` | Express.js |
| `{{API_BASE_PATH}}` | /api/v1 |
| `{{DATABASE_DRIVER}}` | node-postgres (`pg`) |
| `{{AUTH_USER_FIELD}}` | req.user.id |
| `{{DEFAULT_STATUS}}` | OPEN |
| `{{SQL_PLACEHOLDER_STYLE}}` | $1, $2, $3 |
| `{{PASSWORD_LIBRARY}}` | bcrypt |
