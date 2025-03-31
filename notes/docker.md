cker Course Notes

## 🐋 Docker Explained

### 🤔 What is Docker?
- **Containerization Platform**: Packages applications and dependencies into isolated containers.
- **Lightweight Alternative to VMs**:
  - Containers share the host OS kernel (no full OS required).
  - Faster startup times (~seconds vs minutes for VMs).
  - Smaller footprint (e.g., Nginx container: <100 MB vs Ubuntu VM: ~1 GB).

![Docker vs VM Architecture](https://i.imgur.com/TRNkLw5.png)

---

## 📦 Docker Registries

### 🔒 What Are Registries?
Repositories for storing/pulling Docker images:
- **Public Registries**:
  - Docker Hub (default)
  - GitHub Container Registry (GHCR)
- **Private Registries**:
  - Self-hosted Docker Registry
  - GitLab Container Registry
  - Azure Container Registry (ACR)
  - Amazon Elastic Container Registry (ECR)

```bash
docker pull nginx:latest         # Pull from Docker Hub
docker push myregistry.com/app  # Push to private registry
```

## 🛠️ Dockerfiles

### 📝 What is a Dockerfile?
A text file with instructions to build a Docker image:

```dockerfile
FROM alpine:3.15        # Base image (OS)
COPY app.py /app        # Copy files
RUN pip install flask   # Install dependencies
EXPOSE 80               # Open port
CMD ["python", "/app/app.py"]  # Default command
```

### 🔍 Base Image Best Practices
- Use small base images (e.g., alpine).
- Avoid outdated OS versions.
- Chain commands in RUN to reduce layers:

```dockerfile
RUN apt-get update &&     apt-get install -y nginx
```

## 🖥️ Docker Commands Cheat Sheet

| Command            | Description                   | Example |
|--------------------|-----------------------------|---------|
| `docker build`    | Build image from Dockerfile | `docker build -t myapp:v1 .` |
| `docker run`      | Start a container           | `docker run -d -p 80:80 --name web nginx` |
| `docker ps`       | List running containers     | `docker ps -a` (show all) |
| `docker exec`     | Run command in a container  | `docker exec web ls /app` |
| `docker logs`     | View container logs        | `docker logs web` |
| `docker stop`     | Stop container             | `docker stop web` |
| `docker rm`       | Delete container           | `docker rm web` |
| `docker rmi`      | Delete image               | `docker rmi nginx` |

## 🔒 Docker Security Recommendations

### 🛡️ Runtime Flags for Security

```bash
docker run   --memory 512m \                  # Limit memory
  --cpus 1.5 \                     # Limit CPU
  --read-only \                    # Restrict filesystem writes
  --restart=on-failure:5 \         # Auto-restart policy
  --security-opt=no-new-privileges # Prevent privilege escalation
```

### 🧹 Image Hygiene
- Scan images for vulnerabilities with `docker scan`.
- Avoid `latest` tag in production; use specific versions.
- Remove unused images: `docker image prune`.

## 🧪 Docker Hands-On Demo

### 🚀 Build & Run a Simple Web Server

Create Dockerfile:

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html
```

Build image:

```bash
docker build -t my-nginx .
```

Run container:

```bash
docker run -d -p 8080:80 --name webserver my-nginx
```

Access at `http://localhost:8080` 🎉

## 🚢 Docker Compose

### 📄 What is Docker Compose?
Tool for defining/running multi-container apps via YAML:

```yaml
version: '3.8'
services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
  db:
    image: postgres:13
    environment:
      POSTGRES_PASSWORD: mysecretpassword
```

### 🛠️ Compose Commands

```bash
docker-compose up -d    # Start services
docker-compose down     # Stop and remove
docker-compose logs     # View logs
```

### 🧪 Docker Compose Hands-On Demo

Create `docker-compose.yml`:

```yaml
version: '3.8'
services:
  frontend:
    image: nginx:alpine
    ports:
      - "8080:80"
  backend:
    image: node:14
    command: npm start
```

Start services:

```bash
docker-compose up -d
```

Verify:

```bash
docker-compose ps
```
