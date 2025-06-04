# Docker Notes


## 🟢 1. Introduction to Containers & Docker

### What are Containers?

* Lightweight, standalone executable package of software.
* Includes code, runtime, system tools, libraries, settings.
* Uses host OS kernel (unlike VMs that use full OS).

### Why Docker?

* Docker simplifies containerization.
* Ensures consistency across environments (dev, test, prod).
* Fast startup and efficient resource usage.

### Virtualization vs Containerization

| Feature        | Virtualization | Containerization |
| -------------- | -------------- | ---------------- |
| Isolation      | Full OS per VM | Shared OS kernel |
| Speed          | Slower startup | Fast startup     |
| Resource usage | High           | Low              |

### Docker Architecture

```
+------------------+
|     Docker CLI   |  <-- Client
+------------------+
          |
          v
+------------------+
|  Docker Daemon   |  <-- Server
|   (dockerd)      |
+------------------+
     |    |     |
     v    v     v
 Images Containers Networks
```

* **Client**: Interface for user (docker CLI)
* **Daemon**: Runs in background, manages containers
* **Images**: Blueprint to create containers
* **Containers**: Running instances
* **Registries**: Docker Hub, etc.

---

## 🔹 2. Installing Docker

* Install Docker Desktop (Windows/macOS)
* For Linux: use `apt`, `dnf`, or `yum`.

```bash
docker --version
docker info
```

---

## 🟡 3. Working with Docker Images

### What is a Docker Image?

* Read-only template with OS, app, libraries, etc.

### Commands

```bash
docker pull nginx
docker images
docker rmi nginx
docker build -t myapp .
```

### Dockerfile Example

```dockerfile
FROM node:16
COPY . /app
WORKDIR /app
RUN npm install
CMD ["node", "index.js"]
```

---

## 🟠 4. Working with Containers

```bash
docker run -d -p 3000:3000 myapp
docker ps
docker stop <id>
docker start <id>
docker exec -it <id> bash
docker run -v ./data:/app/data myapp
```

---

## 🔴 5. Dockerfile – Deep Dive

### Layered Architecture

* Each Dockerfile instruction = 1 layer.
* Docker caches layers.

### Multi-Stage Build

```dockerfile
FROM node:16 AS builder
WORKDIR /app
COPY . .
RUN npm run build

FROM nginx
COPY --from=builder /app/dist /usr/share/nginx/html
```

---

## 🔳 6. Docker Volumes & Storage

### Types:

* **Anonymous**: `docker run -v /app/data myapp`
* **Named**: `docker volume create myvol`
* **Bind Mounts**: `-v $(pwd)/data:/data`

```bash
docker volume create mydata
docker run -v mydata:/data myapp
```

---

## 🌤️ 7. Docker Networking

### Modes:

* **Bridge (default)**
* **Host**
* **None**
* **Overlay** (for Swarm)

```bash
docker network create mynetwork
docker network connect mynetwork container1
```

---

## ⚪ 8. Docker Compose

Used for multi-container setups.

### docker-compose.yml

```yaml
version: '3'
services:
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
  redis:
    image: redis
```

### Commands:

```bash
docker-compose up
docker-compose down
```

---

## ⚪ 9. Docker Registry & Image Management

* **Docker Hub**: Public registry
* `docker login`
* `docker push <image>`
* `docker pull <image>`

For private: use tools like **Harbor**.

---

## 🟧 10. Docker Security

* **Namespaces**: Container isolation
* **Resource Limits**:

```bash
docker run --memory=256m --cpus=1 myapp
```

* **Docker Bench**: Audit tool

---

## 🟨 11. Docker Swarm

Docker Swarm = Clustering + Load balancing

```bash
docker swarm init
docker service create --replicas 3 --name web nginx
docker service scale web=5
```

---

## 🟩 12. Docker with CI/CD Tools

### Example (GitHub Actions)

```yaml
- name: Build & Push Docker image
  run: |
    docker build -t myapp .
    docker login -u $DOCKER_USER -p $DOCKER_PASS
    docker push myapp
```

CI tools: **Jenkins**, **GitLab CI**, **GitHub Actions**

---

## 🔹 13. Docker in Real Projects

* Use with React, Node.js, MongoDB, PostgreSQL
* Replace local dev setup
* Test microservices locally

---

## 🔴 14. Troubleshooting and Best Practices

### Useful Commands

```bash
docker logs <container>
docker inspect <container>
docker system prune
```

### Best Practices

* Use `.dockerignore`
* Use minimal base images
* Tag images properly

---

## 🧠 15. Bonus: Docker vs Kubernetes

| Feature    | Docker                | Kubernetes                   |
| ---------- | --------------------- | ---------------------------- |
| Use Case   | Single-host, dev/test | Multi-host, production scale |
| Scaling    | Manual or Swarm       | Automatic                    |
| Discovery  | Limited               | Built-in                     |
| Management | Simple                | Complex but powerful         |
