# Docker Commands

This file lists **basic and commonly used Docker commands** along with their purpose. These commands are used to manage Docker images and containers.

---

## Docker Image Commands

### `docker pull`
Used to **download an image** from Docker Hub or another registry.

```bash
docker pull python
```

### `docker images`
Used to list all Docker images available on the local system.

```bash
docker images
```

### `docker rmi`
Used to remove a Docker image from the local system.

```bash
docker rmi image_id
```

---

## Docker Container Commands

### `docker run`
Used to create and start a container from an image.

```bash
docker run python
```

### `docker run -it`
Used to run a container in interactive mode.

```bash
docker run -it python
```

- `-i` 	 interactive
- `-t` 	 terminal

### `docker ps`
Used to list running containers.

```bash
docker ps
```

### `docker ps -a`
Used to list all containers (running and stopped).

```bash
docker ps -a
```

### `docker stop`
Used to stop a running container.

```bash
docker stop container_id
```

### `docker rm`
Used to remove a stopped container.

```bash
docker rm container_id
```

---

## Port Mapping Commands

### `docker run -p`
Used to map a container port to a host port.

```bash
docker run -p 5000:5000 image_name
```

Format:

```yaml
host_port : container_port
```

---

## Environment Variable Commands

### `docker run -e`
Used to set environment variables inside a container.

```bash
docker run -e ENV_NAME=value image_name
```

---

## Useful Combined Example

```bash
docker run -it -p 5000:5000 -e PORT=5000 python
```

This command:
- runs the container interactively
- maps port 5000
- sets an environment variable

---

## Important Notes 

- Containers are isolated by default
- Ports must be exposed to access applications
- Environment variables help configure applications
- Images are reusable
- Containers can be deleted after use

---

## Summary

- Docker commands manage images and containers
- `docker pull` downloads images
- `docker run` starts containers
- `docker ps` checks container status
- `docker stop` and `docker rm` clean up resources

These commands form the foundation of working with Docker.
