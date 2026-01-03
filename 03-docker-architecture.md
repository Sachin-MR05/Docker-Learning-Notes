# Docker Architecture

To understand how Docker works internally, it is important to understand its **architecture**.  
Docker follows a **client–server architecture**, where different components work together to build, run, and manage containers.

---

## High-Level View of Docker Architecture

Docker consists of the following main components:

- Docker Client
- Docker Daemon
- Docker Engine
- Docker Images
- Docker Containers
- Docker Registry

All these components communicate with each other to manage containerized applications.

---

## Docker Client

The **Docker Client** is the interface used by users to interact with Docker.

- It is commonly accessed through the **Docker CLI**
- Commands like `docker run`, `docker build`, and `docker pull` are executed from the client
- The client sends requests to the Docker Daemon

The Docker Client itself does not perform heavy operations.  
It only **communicates instructions** to the daemon.

---

## Docker Daemon

The **Docker Daemon** (`dockerd`) is the core background service of Docker.

It is responsible for:
- Building Docker images
- Running containers
- Managing container lifecycle
- Handling networks and volumes

The daemon listens for requests from the Docker Client and performs the requested actions.

---

## Docker Engine

The **Docker Engine** is the complete platform that enables containerization.

It includes:
- Docker Daemon
- Docker REST API
- Docker CLI

The Docker Engine acts as the **runtime environment** that makes containers possible.

---

## Docker REST API

The **Docker REST API** allows communication between the Docker Client and Docker Daemon.

- The client sends requests through the REST API
- The daemon processes these requests and returns responses

This design allows Docker to:
- Support remote clients
- Integrate with external tools
- Enable automation and orchestration

---

## Docker Images

Docker Images are:
- Read-only templates
- Built using Dockerfiles
- Stored locally or in registries

Images are used by the Docker Daemon to create containers.

---

## Docker Containers

Docker Containers are:
- Running instances of images
- Managed by the Docker Daemon
- Isolated from each other and the host system

Containers are created, started, stopped, and removed by the daemon.

---

## Docker Registry

A **Docker Registry** is a storage location for Docker images.

Common registries include:
- Docker Hub (public registry)
- Private registries
- Cloud registries (AWS ECR, Azure ACR, GCP)

Docker pulls images from registries and pushes images to them when required.

---

## Docker Workflow (Step-by-Step)

1. User runs a command using Docker CLI
2. Docker Client sends the request to Docker Daemon
3. Docker Daemon:
   - pulls image (if not available)
   - creates container
   - runs the container
4. Output is returned to the client

This workflow happens transparently in the background.

---

## Summary

Docker architecture is based on a **client–server model** where:

- Docker Client sends commands
- Docker Daemon executes them
- Docker Engine manages the entire system
- Images act as blueprints
- Containers act as running applications
- Registries store and distribute images

Understanding Docker architecture helps in debugging, automation, and efficient container usage.
