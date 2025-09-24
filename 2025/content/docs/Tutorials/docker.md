## 1. Introduction to Docker for Robotics

🎯 **Learning Objectives**

- Understand what Docker is and why it's useful in robotics
- Identify key Docker concepts (images, containers, Dockerfiles)
- Learn the benefits of using Docker for reproducibility and isolation

### What is Docker?

Imagine your laptop is a kitchen. Docker is like having a bunch of meal kits — everything you need to cook a specific meal (or run a software project) is packed neatly together. No missing ingredients, no mess.

Docker allows you to package an application and all its dependencies into a **container**. This container can run on any computer with Docker installed, regardless of the operating system.

> 📘 Learn more: [Docker Overview](https://docs.docker.com/get-started/overview/)

### Why Use Docker in Robotics?

- ✅ **Reproducibility**: Everyone on your team runs the same setup.
- ✅ **Isolation**: No conflicts between projects.
- ✅ **Portability**: Move between laptops, labs, or robots with no reinstallation.

### Core Docker Concepts (with Visual Aid)

```
+--------------------------+
|         Image           | <-- Recipe for your container (like a blueprint)
+--------------------------+
|         Dockerfile      | <-- Instructions to build the image
+--------------------------+
|         Container        | <-- A running instance of the image
+--------------------------+
```

> 📘 Learn more: [Docker Images vs Containers](https://docs.docker.com/get-started/)

### ✅ Good Habits Checklist

- [ ] Use `Dockerfile` instead of installing software manually
- [ ] Document what each command does using comments
- [ ] Never hardcode credentials in Dockerfiles
- [ ] Always mount volumes to avoid losing work

🎥 **Coming Soon:** Visual terminal demo — _docker build and run_

---

## 2. Getting Hands-On with Docker

> 🎥 Visual: `docker run` in action _(Insert terminal recording GIF)_

### Installation

- [Install Docker for your OS](https://docs.docker.com/get-docker/)

### Core Commands

```bash
# Download an existing image from Docker Hub
docker pull ubuntu

# Build a custom image from a Dockerfile
docker build -t my_image .

# Run an interactive container
docker run -it my_image

# List running containers
docker ps

# Start a container
docker start -ai <container-id>

# Stop a container
docker stop <container-id>

# Remove a container
docker rm <container-id>
```

> 📘 Learn more: [Docker CLI Reference](https://docs.docker.com/engine/reference/commandline/docker/)

### ✅ Good Habits Checklist

- [ ] Use `--rm` to clean up containers automatically when testing
- [ ] Clean up regularly using `docker system prune`
- [ ] Use `--name` to identify containers more easily

---
