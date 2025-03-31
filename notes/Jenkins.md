# 🧩 Jenkins Notes

## 🤖 What is Jenkins?

Jenkins is an **open-source automation server** used primarily for **CI/CD (Continuous Integration and Continuous Delivery)**.  
It provides flexibility and control over how automation is performed in software development workflows.

---

## ⚙️ Key Features

- 🖥️ **Full control over the server** – Unlike many CI/CD SaaS platforms, Jenkins runs on your own infrastructure.
- 🔌 **Highly configurable** – Almost anything you can do on a server, you can do via Jenkins.
- 🧩 **Plugin ecosystem** – Jenkins by itself is minimal, but its plugin architecture allows vast extensibility.

---

## 🛠️ How Jenkins Works

- 🧱 Jenkins runs **jobs**. Jobs are tasks you define, such as:
  - Build/compile/test code
  - Deploy applications
  - Run scripts or scheduled tasks
- 📅 Jobs can be **scheduled** to run:
  - At specific times
  - When a commit is pushed
  - After another job completes

---

## 📁 Job Workspaces

Each job has its **own workspace**:
- Temporary or persistent
- Can be cleaned automatically

---

## 🧪 Jenkins Configuration Modes

- 🧍 **Standalone** – Single-node Jenkins server running all jobs
- 👥 **Agent-Master (Controller-Agent)** – The **controller** manages coordination, while **agents** execute the jobs
  - Communication via **UI** and **REST API**

---

## 💡 Summary

| Feature            | Description |
|--------------------|-------------|
| Automation Server  | Self-hosted automation for CI/CD |
| Plugin Support     | Extend functionality for virtually any use case |
| Flexible Scheduling| Run jobs on custom triggers or intervals |
| Workspace Isolation| Each job gets a clean or reusable workspace |
| Scalable           | Use agent-controller mode for distributed execution |