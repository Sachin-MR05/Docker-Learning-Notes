# Docker Images vs Containers

Understanding the difference between **Docker Images** and **Docker Containers** is one of the most important concepts in Docker.

Many beginners confuse these two, but they serve very different purposes.

---

## What is a Docker Image?

A **Docker Image** is a **read-only template** that contains everything required to run an application, such as:

- Application code
- Required libraries
- Dependencies
- Runtime environment
- Configuration instructions

An image does **not run by itself**.  
It only provides the **instructions and environment** needed to create a container.

### Key characteristics of a Docker Image

- Read-only
- Static
- Stored on disk
- Used as a blueprint
- Can be shared through Docker Hub or private registries

---

## What is a Docker Container?

A **Docker Container** is a **running instance of a Docker image**.

When an image is executed using Docker, it becomes a container.

A container:
- runs the application
- consumes CPU and memory
- can be started, stopped, or deleted

### Key characteristics of a Docker Container

- Writable
- Dynamic
- Uses system resources
- Exists only while running (unless stopped)
- Isolated from other containers

---

## Image vs Container: Class vs Object Analogy

A simple way to understand this is by using an **Object-Oriented Programming (OOP)** analogy.

| OOP Concept | Docker Concept |
|------------|----------------|
| Class | Image |
| Object | Container |

- A **class** defines structure but does not execute
- An **object** is created from a class and runs in memory
- Similarly:
  - An **image** defines how an application should run
  - A **container** is the actual running application

---

## One Image, Multiple Containers

From a single Docker image:
- Multiple containers can be created
- Each container runs independently
- Each container is isolated

Example:
- One image → Container A
- Same image → Container B
- Same image → Container C

All containers:
- behave the same
- do not interfere with each other

---

## Image Does Not Use Runtime Memory

An important point from the notes:

- A **Docker image does not consume CPU or memory**
- A **Docker container consumes CPU and memory**

The image only occupies **disk space**, while the container is an active process.

---

## Lifecycle Comparison

### Docker Image lifecycle
- Built using a Dockerfile
- Stored locally or in a registry
- Reused multiple times
- Does not change once created

### Docker Container lifecycle
- Created from an image
- Starts running
- Can be stopped or restarted
- Can be deleted after use

---

## Why This Difference Matters

Understanding image vs container helps you:

- Avoid accidental data loss
- Design better workflows
- Debug issues correctly
- Use Docker efficiently

For example:
- Changes inside a container are **temporary**
- To make permanent changes, the **image must be rebuilt**

---

## Summary

In simple terms:

- **Image** → Blueprint / Template / Class
- **Container** → Running instance / Object
- Images are static and reusable
- Containers are dynamic and disposable
- One image can create many containers

This concept is fundamental for understanding Dockerfiles, Docker Hub, and Docker Compose.
