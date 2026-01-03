# Docker Compose

To manage applications that use **multiple containers**, Docker provides a tool called **Docker Compose**. Docker Compose allows us to **define and run multi-container applications** using a single configuration file.

---

## High-Level View of Docker Compose

Docker Compose is used when an application consists of multiple services such as:

- Application container
- Database container
- Cache container
- Backend / API services

All these services are defined and managed together using **Docker Compose**.

---

## What is Docker Compose?

**Docker Compose** is a tool that helps us:

- run multiple containers together
- define application services in one file
- manage containers as a single unit

Docker Compose uses a file called:

```yaml
docker-compose.yml
```

This file contains the configuration of all services required for an application.

---

## docker-compose.yml File

The `docker-compose.yml` file defines:

- services (containers)
- images or build instructions
- ports
- volumes
- environment variables
- networks

This file acts as a **blueprint for the entire application setup**.

---

## Services in Docker Compose

A **service** represents a container in Docker Compose.

Each service can:
- use an image
- build from a Dockerfile
- expose ports
- mount volumes

Example services:
- web application
- database
- API server

All services run together using Docker Compose.

---

## Docker Compose Command Interface

Docker Compose is controlled using the Docker Compose CLI.

Common command:

```bash
docker compose up
```

This command:

- builds images (if needed)
- creates containers
- starts all services together

---

## Docker Compose for Development

Docker Compose is commonly used in development environments.

It allows developers to:

- run the full application locally
- maintain the same environment across systems
- avoid manual container management

Using Docker Compose:

- all developers run the same setup
- environment mismatch is avoided

---

## Volumes in Docker Compose

Docker Compose supports volumes, which allow file sharing between:

- host system
- container

This enables:

- live code changes
- no rebuild required during development
- faster development workflow

---

## Networking in Docker Compose

Docker Compose automatically creates a network for all services.

- Containers can communicate using service names
- No need to configure IP addresses manually

This simplifies inter-container communication.

---

## Docker Compose Workflow (Step-by-Step)

1. Developer writes `docker-compose.yml`
2. Runs `docker compose up`
3. Docker Compose:
   - builds images (if required)
   - creates networks
   - creates volumes
   - starts containers
4. All services run together

This workflow happens automatically.

---

## When to Use Docker Compose

Docker Compose is useful when:

- application has multiple services
- working in a team
- developing locally
- testing full application stack

It is not intended for large-scale production orchestration.

---

## Summary

Docker Compose simplifies multi-container management by:

- defining services in one file
- running multiple containers together
- providing consistent development environments
- reducing manual Docker commands

Docker Compose acts as a project-level management tool for containerized applications.