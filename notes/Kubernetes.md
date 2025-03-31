# ☸️ Kubernetes

## ❓ What is Kubernetes?
- Also known as **k8s** (there are 8 letters between 'K' and 'S')
- A **container orchestration** system designed for high scalability
- Name comes from Greek: “kubernetes” = *helmsman* or *pilot*
- 🏢 Preferred for enterprise environments with large numbers of containers

---

## 🏗️ Core Concepts
- **Container**: runs inside a **Pod**
- **Pod**: the smallest deployable unit in Kubernetes
- **Deployment**: defines how Pods are managed (written in YAML)
  - For example: `kubectl apply -f nginx-deployment.yaml`
- **ReplicaSet**: created by a Deployment to maintain the desired number of Pods
- **Cluster**: a set of nodes that run Pods

### Basic Flow
```
Deployment → ReplicaSet → Pods → Containers
```

---

## ⚙️ Cluster Components

### Control Plane
- **API Server**: the RESTful endpoint for the cluster
- **Controller Manager**: runs controllers that handle tasks like scaling
- **Scheduler**: decides on which node each Pod should run
- **etcd**: a key-value store for cluster state

### Nodes
- **kubelet**: agent running on each node, manages Pods
- **kube-proxy**: manages networking rules for exposing services
- **Container Runtime** (e.g., Docker, containerd): runs the containers

---

## 🔧 Administration

### CLI: `kubectl`
- **kubectl get**: list resources
- **kubectl describe**: detailed info about a resource
- **kubectl create**: create a resource from a YAML/JSON manifest
- **kubectl delete**: remove a resource
- **kubectl logs**: show container logs in a Pod
- **kubectl exec**: run commands inside a container

### UI
- **Kubernetes Dashboard**: basic web interface for managing cluster resources

### API
- Exposed via HTTP (REST)
- Used by client libraries (Python, Go, Java, etc.) and by the CLI/UI

---

## ☁️ Managed Kubernetes
- **GKE** (Google Kubernetes Engine)
- **EKS** (Amazon Elastic Kubernetes Service)
- **AKS** (Azure Kubernetes Service)

These providers handle most control plane components so you can focus on deployments.

---

## 🔒 Security in Kubernetes

### The 4 C’s Model
1. **Cloud** (infrastructure)
2. **Cluster** (Kubernetes configuration)
3. **Containers** (Docker images)
4. **Code** (the application itself)

### Cloud (Infrastructure)
- ⬆️ Keep servers & systems updated
- 🔐 Strong authentication & 2FA/MFA
- 🔍 Limit port exposure
- 🔑 Principle of least privilege
- ✨ Data at rest encryption
- 🌐 Follow CIS Benchmarks & best practices

### Cluster (Kubernetes Config)
- **Authentication**:
  - X509 certificates
  - Tokens
  - OIDC
  - Service Accounts
  - Webhooks
  - Proxies
- **RBAC** (Role-Based Access Control):
  - `Role` vs `ClusterRole`
  - `RoleBinding` vs `ClusterRoleBinding`
- **Secrets**:
  - Keep credentials outside source code
  - Mount as volumes or environment variables
- **etcd**: enable encryption (KMS is preferred)
- **Network Policies**:
  - Define allowed ingress/egress traffic between Pods/Services
  - Example:

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: example-network-policy
  namespace: default
spec:
  podSelector:
    matchLabels:
      role: application
  policyTypes:
  - Ingress
  - Egress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          role: application
    ports:
    - port: 443
    - port: 80
  egress:
  - to:
    - ipBlock:
        cidr: 8.8.8.8/32
    ports:
    - port: 53
      protocol: UDP
```

---

### Containers (Docker)
- Keep images updated (security patches)
- Use minimal base images
- Enforce resource limitations (`cpu`, `memory`)
- Avoid running as `root` whenever possible

### Code (Application)
- Follow **OWASP** guidelines:
  - Top 10
  - ZAP
  - ASVS
  - Cheat sheets
- Manage third-party dependencies (SCA)
- Perform security testing (SAST, DAST, penetration testing)

---

## 💡 General Tips
- **Namespaces**: isolate teams or environments
- **Labels & Selectors**: organize objects for easy management
- **Helm**: package manager for Kubernetes
- **Monitoring**: integrate with Prometheus, Grafana
- **Logging**: gather logs with Fluentd/Elasticsearch

