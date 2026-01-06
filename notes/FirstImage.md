# First Docker Image: House Prediction Project

This page explains how the Dockerfile builds your house price prediction app into an image, how that image appears in Docker Desktop, and how the running container looks once started.

## Dockerfile Essentials
- **FROM:** Base image (e.g., a lightweight Python). Sets the runtime your app needs.
- **WORKDIR:** Sets the working directory inside the image (e.g., `/app`).
- **COPY:** Copies files into the image (e.g., `requirements.txt` and source code).
- **RUN:** Executes build-time commands (e.g., `pip install -r requirements.txt`).
- **EXPOSE:** Documents the port your app listens on (example: `5000`).
- **CMD:** Defines the default command to start your app.

Example Dockerfile for a Python-based house prediction app (adjust entrypoint and port to your project):

```dockerfile
FROM python:3.11-slim
WORKDIR /app

# Install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

# If your app serves on port 5000, document it
EXPOSE 5000

# Start the app (replace with your real entrypoint)
CMD ["python", "app.py"]
```

## Build, Tag, and Run
- **Build the image:**

```bash
docker build -t house-prediction:latest .
```

Note: `docker build -t requirements.txt` is not a valid command. The `-t` flag sets an image tag (e.g., `house-prediction:latest`). `requirements.txt` belongs in the Dockerfile to install dependencies.

- **Run a container from the image (example mapping port 5000):**

```bash
docker run -d -p 5000:5000 --name house-prediction house-prediction:latest
```

## Visuals: Dockerfile, Image, and Container

- Dockerfile structure used for the build:

![Dockerfile structure for house prediction](../diagrams/DockerFile.png)

- Image created and visible in Docker Desktop:

![Image created in Docker Desktop](../diagrams/DockerImage.png)

- Running container in Docker Desktop:

![Running container in Docker Desktop](../diagrams/DockerContainer.png)

## Tips
- If your app uses a different port, update `EXPOSE` and the `-p host:container` mapping accordingly.
- For non-Python apps, swap the base image and install steps to match your stack.
