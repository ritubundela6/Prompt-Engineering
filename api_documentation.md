# Task Tracker API Documentation

```yaml
openapi: 3.0.3
info:
  title: Task Tracker API
  version: 1.0.0
  description: B2B REST API for authenticated task tracking and status management.
servers:
  - url: /api/v1
paths:
  /tasks:
    post:
      summary: Create a new task
      tags: [Tasks]
      security:
        - bearerAuth: []
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateTaskRequest'
      responses:
        '201':
          description: Task created successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/TaskResponse'
        '400':
          description: Invalid request body or status
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorResponse'
  /tasks/{id}:
    get:
      summary: Get a task by ID
      tags: [Tasks]
      security:
        - bearerAuth: []
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: integer
            minimum: 1
      responses:
        '200':
          description: Task retrieved successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/TaskResponse'
        '400':
          description: Invalid task ID
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorResponse'
        '404':
          description: Task not found
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ErrorResponse'
components:
  securitySchemes:
    bearerAuth:
      type: http
      scheme: bearer
      bearerFormat: JWT
  schemas:
    CreateTaskRequest:
      type: object
      required: [title]
      properties:
        title:
          type: string
          example: Prepare inventory report
        description:
          type: string
          nullable: true
        status:
          type: string
          enum: [OPEN, IN_PROGRESS, COMPLETED]
          default: OPEN
        due_date:
          type: string
          format: date
          nullable: true
    Task:
      type: object
      properties:
        id: { type: integer, example: 101 }
        user_id: { type: integer, example: 7 }
        title: { type: string }
        description: { type: string, nullable: true }
        status: { type: string, enum: [OPEN, IN_PROGRESS, COMPLETED] }
        due_date: { type: string, format: date, nullable: true }
        created_at: { type: string, format: date-time }
    TaskResponse:
      type: object
      properties:
        data:
          $ref: '#/components/schemas/Task'
    ErrorResponse:
      type: object
      properties:
        error: { type: string }
```
