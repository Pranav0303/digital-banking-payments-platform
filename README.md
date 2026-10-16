# Banking Platform

A mini digital banking / payments platform: Spring Boot REST API for accounts and
transfers, a rule-based fraud/risk engine, Kafka event streaming, a React dashboard,
and an AI-assisted natural-language query endpoint over transaction history.

## Stack

- **Backend**: Java 25, Spring Boot 4.1 (Web, Data JPA, Kafka, Validation, Actuator)
- **Database**: H2 (local dev, in-memory) / PostgreSQL (Docker)
- **Messaging**: Apache Kafka (transaction events)
- **Frontend**: React (Vite)
- **AI**: Claude API for natural-language spending queries
- **Containerization**: Docker Compose (postgres, kafka, backend, frontend)

## Local development (no Docker required)

Backend runs against in-memory H2 by default:

```bash
cd backend
./mvnw spring-boot:run
```

- API: http://localhost:8080
- H2 console: http://localhost:8080/h2-console (JDBC URL `jdbc:h2:mem:bankingdb`)

Frontend:

```bash
cd frontend
npm install
npm run dev
```

## Full stack via Docker Compose

Requires Docker Desktop or OrbStack. Runs Postgres + Kafka + backend + frontend:

```bash
docker compose up --build
```

## Project layout

```
backend/    Spring Boot API (domain, repository, service, controller, fraud, kafka)
frontend/   React dashboard (Vite)
docker-compose.yml
```
