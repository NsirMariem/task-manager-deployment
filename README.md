# Task Manager Full Stack

## Project architecture

This workspace contains two separate projects:

- `task-manager-frontend`
  - React + Vite + TypeScript frontend
  - Axios for API calls
  - React Router for navigation
  - Protected routes and cookie-based authentication

- `task-manager-copilot-demo`
  - Spring Boot 3 REST API
  - Java 17, Spring Data JPA, H2 database in development
  - JWT authentication with httpOnly cookie strategy
  - OpenAPI/Swagger documentation

A root-level `docker-compose.yml` ties both services together for full-stack local development.

## Run with docker-compose

From the workspace root (`devProjects`):

```bash
docker compose up --build
```

Then open:

- Frontend: `http://localhost:4173`
- Backend: `http://localhost:8081`

To stop the stack:

```bash
docker compose down
```

## Run locally

### Backend

From `task-manager-copilot-demo`:

```bash
mvn clean package
mvn spring-boot:run
```

The backend will run on `http://localhost:8081`.

### Frontend

From `task-manager-frontend`:

```bash
npm install
npm run dev
```

The frontend will run on `http://localhost:5173`.

If you use the API locally, make sure the backend is running and set `VITE_API_BASE_URL` appropriately.

## AI agents configured in this project

This workspace leverages Copilot-assisted AI agents for development review and automation, including:

- `security-auditor`
- `frontend-reviewer`
- `devops-agent`

These agents have been used to review authentication, security, frontend behavior, and CI/CD/container configuration.
