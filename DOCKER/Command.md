# 🐳 Docker Commands Cheat Sheet



## 🟢 General

| Command | Description |
|---------|-------------|
| `docker --version` | Show Docker version |
| `docker info` | Show Docker system information |
| `docker help` | List all Docker commands |

---

## 🟡 Images

| Command | Description |
|---------|-------------|
| `docker pull <image>` | Download image from Docker Hub |
| `docker images` | List downloaded images |
| `docker rmi <image>` | Remove an image |
| `docker build -t <name> .` | Build image from Dockerfile |

---

## 🟠 Containers

| Command | Description |
|---------|-------------|
| `docker run <image>` | Run container from image |
| `docker run -d <image>` | Run in detached (background) mode |
| `docker run -it <image>` | Run with interactive terminal |
| `docker ps` | List running containers |
| `docker ps -a` | List all containers (running + stopped) |
| `docker start <container>` | Start an existing container |
| `docker stop <container>` | Stop a running container |
| `docker restart <container>` | Restart a container |
| `docker rm <container>` | Remove a container |
| `docker exec -it <container> <command>` | Execute command in running container |
| `docker attach <container>` | Attach terminal to running container |
| `docker logs <container>` | Show container logs |

---

## 🔵 Networking

| Command | Description |
|---------|-------------|
| `docker network ls` | List all Docker networks |
| `docker network create <name>` | Create a custom network |
| `docker network inspect <name>` | Show network details |
| `docker network connect <network> <container>` | Connect container to a network |

---

## 🟣 Volumes & Storage

| Command | Description |
|---------|-------------|
| `docker volume ls` | List volumes |
| `docker volume create <name>` | Create named volume |
| `docker volume inspect <name>` | Show volume info |
| `docker volume rm <name>` | Delete volume |
| `-v <host>:<container>` | Mount host directory in container |

---

## ⚫ Dockerfile Keywords

| Keyword | Description |
|---------|-------------|
| `FROM` | Define base image |
| `RUN` | Execute command at build time |
| `COPY` | Copy files to image |
| `WORKDIR` | Set working directory |
| `CMD` | Default command to run |
| `ENTRYPOINT` | Configure as executable |
| `EXPOSE` | Open port on container |

---

## ⚪ Docker Compose

| Command | Description |
|---------|-------------|
| `docker-compose up` | Start services from docker-compose.yml |
| `docker-compose down` | Stop and remove services |
| `docker-compose restart` | Restart services |
| `docker-compose logs` | View logs for services |

---

## 🟤 Docker Registry

| Command | Description |
|---------|-------------|
| `docker login` | Authenticate with Docker Hub |
| `docker push <image>` | Upload image to Docker Hub |
| `docker pull <image>` | Download image from Docker Hub |

---

## 🟧 Docker Swarm (Optional)

| Command | Description |
|---------|-------------|
| `docker swarm init` | Initialize Swarm mode |
| `docker service create` | Deploy a new service |
| `docker service ls` | List running services |
| `docker node ls` | List Swarm nodes |

---

## 🟨 Cleanup & Maintenance

| Command | Description |
|---------|-------------|
| `docker system prune` | Remove all unused data |
| `docker image prune` | Remove unused images |
| `docker container prune` | Remove stopped containers |
| `docker volume prune` | Remove unused volumes |

---



