# 🐳 50 Docker Interview Questions & Answers 


### 🟢 Basics

**1. What is Docker?**  
Docker is a tool that helps you run applications inside lightweight, portable containers.

**2. What is a container?**  
A container is a small, isolated environment where your app runs with all its dependencies.

**3. What is the difference between a VM and a container?**  
VMs use full OS, containers share the host OS — so containers are faster and lighter.

**4. What is an image?**  
An image is a blueprint of a container. It includes your app, OS libraries, and dependencies.

**5. What is Docker Hub?**  
It is a cloud-based registry where Docker images are stored and shared.

**6. How do you check the Docker version?**  
`docker --version`

**7. How do you list running containers?**  
`docker ps`

**8. How do you list all containers (including stopped)?**  
`docker ps -a`

**9. What is the command to run a container?**  
`docker run <image>`

**10. How do you stop a running container?**  
`docker stop <container_id>`

---

### 🟡 Images & Dockerfile

**11. How do you pull an image from Docker Hub?**  
`docker pull <image>`

**12. How do you remove an image?**  
`docker rmi <image>`

**13. How do you build an image using a Dockerfile?**  
`docker build -t <image_name> .`

**14. What is a Dockerfile?**  
A text file with instructions to build a Docker image.

**15. What does the `FROM` instruction do?**  
It specifies the base image (e.g., `FROM node:14`).

**16. What does the `COPY` instruction do?**  
It copies files from your system to the image.

**17. What does `CMD` do in a Dockerfile?**  
Specifies the default command to run in the container.

**18. Difference between CMD and ENTRYPOINT?**  
`CMD` can be overridden, `ENTRYPOINT` always runs.

**19. What is the purpose of `EXPOSE`?**  
Tells Docker which port the app runs on.

**20. What is `WORKDIR`?**  
Sets the working directory inside the container.

---

### 🟠 Containers & Management

**21. How do you start a stopped container?**  
`docker start <container_id>`

**22. How do you remove a container?**  
`docker rm <container_id>`

**23. How do you execute a command inside a running container?**  
`docker exec -it <container_id> bash`

**24. What is `-it` used for?**  
`-i` = interactive, `-t` = terminal — together allow shell access.

**25. How to map ports between host and container?**  
`docker run -p 8080:80 <image>`

**26. How to pass environment variables to a container?**  
`docker run -e MY_VAR=value <image>`

**27. What does `-v` flag do?**  
Mounts a volume — `docker run -v host_dir:container_dir <image>`

**28. What is a detached mode?**  
Running container in background using `-d` flag.

**29. How to check logs of a container?**  
`docker logs <container_id>`

**30. How to inspect container details?**  
`docker inspect <container_id>`

---

### 🟣 Volumes & Storage

**31. What is a volume in Docker?**  
A method to persist data outside the container lifecycle.

**32. How to create a volume?**  
`docker volume create myvolume`

**33. How to list all volumes?**  
`docker volume ls`

**34. What are the types of volumes?**  
Anonymous, Named, Host-mounted.

**35. How to mount a named volume?**  
`docker run -v myvolume:/app/data <image>`

---

### 🔵 Networking

**36. What are Docker network types?**  
Bridge (default), Host, None, Overlay.

**37. How to list all networks?**  
`docker network ls`

**38. How to create a custom network?**  
`docker network create mynet`

**39. How to connect a container to a network?**  
`docker network connect mynet <container_id>`

---

### ⚫ Docker Compose

**40. What is Docker Compose?**  
Tool for defining and running multi-container Docker apps.

**41. What is `docker-compose.yml`?**  
A YAML file that defines services, volumes, and networks.

**42. How to start services using Compose?**  
`docker-compose up`

**43. How to stop and remove services?**  
`docker-compose down`

**44. How to restart services?**  
`docker-compose restart`

---

### 🟤 Registry & CI/CD

**45. How to login to Docker Hub?**  
`docker login`

**46. How to push an image to Docker Hub?**  
`docker push <username>/<image>`

**47. How to pull from private registry?**  
`docker pull <registry_url>/<image>`

**48. How is Docker used in CI/CD?**  
To build and deploy containerized apps in pipelines (e.g., GitHub Actions, Jenkins).

---

### 🟥 Bonus / Troubleshooting

**49. How to remove all stopped containers, unused images, volumes?**  
`docker system prune`

**50. When should you choose Kubernetes over Docker?**  
When managing many containers or need auto-scaling, load balancing, and orchestration.



