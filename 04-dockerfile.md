# Dockerfile

## What is a Dockerfile?

A Dockerfile is a **plain text recipe** that tells Docker how to build an image. It defines the base environment, installs dependencies, copies your code, and declares how the container should start.

> Dockerfile = recipe  Docker image = cooked result

---

## Why a Dockerfile is needed

- Repeatable builds instead of manual setup
- Consistent environments across machines
- Easy to share and rebuild images
- Serves as documentation for how the app runs

---

## Basic structure (top to bottom)

1. `FROM` – choose a base image
2. `WORKDIR` – set working directory
3. `COPY` – add project files
4. `RUN` – install dependencies / setup
5. `EXPOSE` – document container port
6. `CMD` – default start command

Each instruction creates a new **image layer**.

---

## Common Dockerfile instructions

### FROM — pick a base image

```dockerfile
FROM python:3.10
```

Every Dockerfile starts with `FROM` (except `scratch`).

### WORKDIR — set working directory

```dockerfile
WORKDIR /app
```

All following instructions run inside `/app`.

### COPY — bring files into the image

```dockerfile
COPY . /app
```

Copies the current project into `/app` in the image.

### RUN — execute build-time commands

```dockerfile
RUN pip install -r requirements.txt
```

Used to install packages, fetch tools, or set up the environment.

### ENV — set environment variables

```dockerfile
ENV PORT=5000
```

Values are available to processes inside the container.

### EXPOSE — document listening port

```dockerfile
EXPOSE 5000
```

Acts as metadata; does not publish the port by itself.

### CMD — default container command

```dockerfile
CMD ["python", "app.py"]
```

Only the final `CMD` in the file takes effect.

---

## RUN vs CMD

| Aspect                  | RUN (build time)                    | CMD (container start)          |
| ----------------------- | ----------------------------------- | ------------------------------ |
| When it executes        | While building the image            | When the container starts      |
| Purpose                 | Install/setup the environment       | Launch the main application    |
| How many allowed        | As many as needed                   | Only the last one is used      |

---

## Example: simple Python app

```dockerfile
FROM python:3.10
WORKDIR /app
COPY . /app
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
```

This image uses Python 3.10, installs dependencies, and starts `app.py` when the container runs.

---

## Key points

- Docker images are immutable; code changes require a rebuild.
- The same Dockerfile produces the same environment everywhere.
- Understanding Dockerfiles is foundational for Docker Hub, Compose, and CI/CD workflows.