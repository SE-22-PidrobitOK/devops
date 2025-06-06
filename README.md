# Pidrobitok Project

This project consists of multiple microservices including an authentication service, job service, and SQL Server database, all orchestrated using Docker Compose.

## Prerequisites

- Docker
- Docker Compose
- Git

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/SE-22-PidrobitOK/devops
cd devops
```

2. Create a `.env` file in the root directory with the following environment variables:
```env
# SQL Server Configuration
SQL_SERVER=sql-server
SQL_USER=sql-user
SQL_PASSWORD=your_strong_password_here

# Database Names
AUTH_DATABASE=auth-db
JOB_DATABASE=job-db

# JWT Configuration
JWT_SECRET=your_jwt_secret_here
JWT_ISSUER=your_issuer_here
JWT_AUDIENCE=your_audience_here
JWT_TOKEN_LIFETIME=3600

# ASP.NET Core Environment
ASPNETCORE_ENVIRONMENT=Development
```

3. Start the services:
```bash
docker compose up
```

The services will be available at:
- SQL Server: localhost:1433
- Nginx (API Gateway): localhost:80
- Auth Service: Internal port 8080
- Job Service: Internal port 8080

## Services

- **SQL Server**: Microsoft SQL Server 2022 Express Edition
- **Nginx**: API Gateway and reverse proxy
- **Auth Service**: Authentication and authorization service
- **Job Service**: Job management service

## Network

All services are connected through a bridge network named `backend-network`.

## Volumes

- `sqldata`: Persistent storage for SQL Server data

## Stopping the Services

To stop all services:
```bash
docker compose down
```

To stop services and remove volumes:
```bash
docker compose down -v
```