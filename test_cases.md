# Task Tracker API Test Cases

## Unit Tests

```javascript
const request = require("supertest");
const app = require("./app");

jest.mock("./db", () => ({ query: jest.fn() }));
const db = require("./db");

describe("Task endpoints", () => {
  const token = "mock-valid-jwt-token";

  beforeEach(() => jest.clearAllMocks());

  test("POST /api/v1/tasks returns 201 for a valid task", async () => {
    db.query.mockResolvedValueOnce({
      rows: [{
        id: 1, user_id: 7, title: "Review client requirements",
        description: "Confirm required fields.", status: "OPEN",
        due_date: "2026-10-10", created_at: "2026-10-02T12:00:00.000Z"
      }]
    });

    const response = await request(app)
      .post("/api/v1/tasks")
      .set("Authorization", `Bearer ${token}`)
      .send({ title: "Review client requirements", status: "OPEN" });

    expect(response.statusCode).toBe(201);
    expect(response.body.data.title).toBe("Review client requirements");
  });

  test("GET /api/v1/tasks/:id returns 404 for a missing task", async () => {
    db.query.mockResolvedValueOnce({ rowCount: 0, rows: [] });

    const response = await request(app)
      .get("/api/v1/tasks/999999")
      .set("Authorization", `Bearer ${token}`);

    expect(response.statusCode).toBe(404);
    expect(response.body.error).toBe("Task not found.");
  });
});
```

## QA Test Matrix

| Test ID | Endpoint | Scenario | Expected result |
|---|---|---|---|
| TC-001 | POST `/api/v1/tasks` | Valid authenticated task creation | HTTP 201 and created task |
| TC-002 | POST `/api/v1/tasks` | Missing title | HTTP 400 |
| TC-003 | POST `/api/v1/tasks` | Invalid status | HTTP 400 |
| TC-004 | GET `/api/v1/tasks/:id` | Existing owned task | HTTP 200 |
| TC-005 | GET `/api/v1/tasks/:id` | Missing or unauthorized task | HTTP 404 |
| TC-006 | GET `/api/v1/tasks/:id` | Non-numeric ID | HTTP 400 |
| TC-007 | POST `/api/v1/login` | SQL-injection-style input | Login fails safely |
