
# 🐳 Docker Course Notes

## 📦 What is Docker?
Docker is a platform for developing, shipping, and running applications in **containers**.

### ✅ Why use Docker?
- 🚀 **Fast deployment**, no external dependencies needed.
- ♻️ **Easy rollback** – images are versioned with tags.
- 📦 **Portability** – containers encapsulate everything, move between environments seamlessly.
- ⚙️ **Not a full VM replacement**, but efficient for single-purpose apps like NGINX in <100 MB vs full OS.
- 🔧 Great for microservices and orchestration (e.g., Kubernetes).

### 🖼️ Containers vs Virtual Machines
| Containers (Docker) | Virtual Machines |
|---------------------|------------------|
| Share host OS kernel | Full OS per VM |
| Lightweight & fast   | Heavier, slower  |
| Start in seconds     | Start in minutes |

---

## 📦 Docker Registries

### 🌐 Public Registries
- **Docker Hub** (default)
- **GitHub Container Registry (GHCR)**

### 🔒 Private Registries
- Self-hosted (Docker registry server)
- GitLab / GitHub
- Azure Container Registry (ACR)
- Amazon Elastic Container Registry (ECR)

```bash
docker pull nginx
docker login myregistry.com
docker push myregistry.com/myapp
```

---

## 📝 Dockerfile

Defines how to build a Docker image.

```Dockerfile
FROM ubuntu:latest
RUN apt-get update && apt-get install -y npm && apt-get clean && rm -rf /var/lib/apt/lists/*
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 80
CMD ["node", "server.js"]
```

---

## 🧱 Base Image

Each Docker image starts from a **base image**, which can be:
- A minimal OS (e.g., `alpine`, `ubuntu`)
- Another image (e.g., `nginx` FROM `alpine`)
- Must ensure base is **secure** and **up to date**

Use:
- `apt-get` for Ubuntu
- `apk` for Alpine

---

## 🛠️ Common Docker Commands

| Command | Description |
|--------|-------------|
| `docker build -t example .` | Build image |
| `docker pull nginx` | Pull image from registry |
| `docker run -v /host:/container` | Run container with volume |
| `docker ps -a` | List all containers |
| `docker kill <id>` | Stop container |
| `docker rm <id>` | Remove container |
| `docker images` | List local images |

---

## 🧪 Testing Docker

### 🧹 Lint Dockerfiles
- `hadolint`
- `dockle`

### 🔍 Scan for vulnerabilities
- `trivy`
- `snyk`

### 📊 Benchmark security
- `docker-bench-security` (CIS Benchmarks)

---

## ✅ Docker Recommendations

- 🐜 Use **minimal base images** (e.g., `alpine`)
- 📁 Use `.dockerignore` to avoid copying secrets
- 🏷️ Use **fixed tags** (`myapp:1.0.0` not `latest`)
- 🚦 Limit resources using flags:
  - `--memory`, `--cpus`, `--read-only`
  - `--restart=on-failure:5`
  - `--security-opt=no-new-privileges:true`

---

## ⚙️ Docker Compose

Define and run **multi-container applications** using YAML.

```yaml
version: '3.8'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example
```

### Useful Commands
```bash
docker-compose up -d     # Start
docker-compose down      # Stop
docker-compose logs      # View logs
```

### Recommendations
- Apply same hardening as Dockerfiles.
- Use non-root users in both:
  - Dockerfile: `USER example`
  - Compose: `user: 1001:1001`