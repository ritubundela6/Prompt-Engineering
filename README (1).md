# Task Tracker REST API

A B2B backend REST API for managing users, tasks, and task-status workflows.

## Description

The Task Tracker REST API supports:

- User registration and login.
- Secure authentication using bearer tokens.
- Task creation and retrieval.
- Task ownership: users can access only their own tasks.
- Status management: `OPEN`, `IN_PROGRESS`, and `COMPLETED`.
- PostgreSQL integration using raw parameterized SQL queries.
- OpenAPI/Swagger documentation and Jest/Supertest tests.

## Technology Stack

- Node.js
- Express.js
- PostgreSQL
- node-postgres (`pg`)
- JWT authentication
- bcrypt password hashing
- Jest and Supertest

## Documentation

- [API Documentation](./api_documentation.md)
- [Test Cases](./test_cases.md)
- [Prompt Library](./prompt_library.md)
- [Software Requirement Document](./software_requirement_document.md)

## Reference Video

[Watch the project reference video](https://youtu.be/Q-S7O_rGYZU)
