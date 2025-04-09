# Todo Application

This repository contains two versions of a full-stack todo application:

1. **project1**: Uses SQLite database with direct SQL queries
2. **project2**: Dockerized version with PostgreSQL and Prisma ORM

## Features

- User authentication (register/login)
- CRUD operations for todos
- JWT authentication
- Frontend interface

## API Endpoints

### Authentication

- `POST /auth/register` - Register a new user

  ```json
  {
    "username": "user@example.com",
    "password": "yourpassword"
  }
  ```

- `POST /auth/login` - Login existing user
  ```json
  {
    "username": "user@example.com",
    "password": "yourpassword"
  }
  ```

### Todos (Require JWT in Authorization header)

- `GET /todos` - Get all todos for authenticated user
- `POST /todos` - Create a new todo
  ```json
  {
    "task": "Finish project"
  }
  ```
- `PUT /todos/:id` - Update a todo (mark as completed)
  ```json
  {
    "completed": true
  }
  ```
- `DELETE /todos/:id` - Delete a todo

## Setup Instructions

### Project1 (SQLite version)

1. Install dependencies:
   ```bash
   npm install
   ```
2. Create `.env` file with:
   ```
   JWT_SECRET=your_secret_key
   ```
3. Start development server:
   ```bash
   npm run dev
   ```

### Project2 (Docker/PostgreSQL version)

1. Start containers:
   ```bash
   docker-compose up -d
   ```
2. Apply Prisma migrations:
   ```bash
   npx prisma migrate dev
   ```
3. Start development server:
   ```bash
   npm run dev
   ```

## Technology Stack

- **Backend**: Node.js, Express
- **Authentication**: JWT, bcrypt
- **Database**:
  - Project1: SQLite
  - Project2: PostgreSQL with Prisma ORM
- **Frontend**: HTML, CSS
- **Containerization**: Docker

## Example Requests

See [todo-app.rest](todo-app.rest) for complete API examples with sample requests.
