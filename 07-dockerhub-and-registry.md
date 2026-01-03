# Docker Hub and Docker Registry

Docker images need a place to be **stored, shared, and downloaded**. This is where **Docker Hub** and **Docker Registries** are used.

---

## What is a Docker Registry?

A **Docker Registry** is a storage system for Docker images.

It allows users to:
- upload images
- download images
- share images with others
- manage image versions

Registries act as a **central location** for Docker images.

---

## What is Docker Hub?

**Docker Hub** is the **default public Docker registry** provided by Docker.

It is used to:
- store Docker images
- share images publicly or privately
- download official images

When we run:

```bash
docker pull python
```

Docker pulls the image from Docker Hub by default.

---

## Types of Docker Registries

### Public Registry
- Images are available to everyone
- Anyone can pull images
- Example: Docker Hub (public repositories)

### Private Registry
- Access is restricted
- Used by companies and teams
- Images are not publicly visible

---

## Official Images on Docker Hub

Docker Hub provides official images such as:

- python
- node
- java
- nginx
- mysql

These images are:

- maintained by trusted sources
- regularly updated
- widely used in production

Using official images is recommended.

---

## Docker Image Tags

Docker images use tags to represent versions.

Example:

```bash
python:3.10
python:latest
```

- `3.10` → specific version
- `latest` → most recent version

Tags help manage different image versions easily.

---

## Pushing Images to Docker Hub

Users can also push their own images to Docker Hub.

General steps:

1. Build Docker image
2. Login to Docker Hub
3. Push image to registry

This allows others to pull and use the same image.

---

## Cloud Container Registries

Apart from Docker Hub, cloud platforms provide their own registries:

- AWS Elastic Container Registry (ECR)
- Azure Container Registry (ACR)
- Google Container Registry (GCR)

These are mainly used for:

- private images
- enterprise applications
- cloud deployments

---

## Why Docker Registry is Important

Docker registries help by:

- centralizing images
- enabling collaboration
- supporting version control
- simplifying deployment
- allowing reuse of images

Registries make Docker workflows scalable and efficient.