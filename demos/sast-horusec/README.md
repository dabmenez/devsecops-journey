# 🛡️ SAST Demo - Using Horusec on Juice Shop

This demo replicates the SAST hands-on activity from the **DevSecOps Fundamentals** course using:

- 📦 [OWASP Juice Shop](https://github.com/juice-shop/juice-shop) — a vulnerable web application used for testing
- 🔍 [Horusec](https://github.com/ZupIT/horusec) — an open-source SAST tool by Zup IT

---

## ✅ What was done?

I used Horusec to scan the Juice Shop source code and detect potential vulnerabilities in the codebase, focusing on the `frontend/` folder.

---

## ⚙️ How to Run the Scan

> Make sure Docker is installed and running.

### 1. Clone Juice Shop

```bash
git clone https://github.com/juice-shop/juice-shop
cd juice-shop/frontend
```

### 2. Run Horusec via Docker

```bash
docker run -v /var/run/docker.sock:/var/run/docker.sock -v $(pwd):/src horuszup/horusec-cli:latest horusec start -p /src -P $(pwd)
```

> 💡 `-p /src`: defines the project path inside the container  
> 💡 `-P $(pwd)`: defines the path for the Horusec config and output outside the container

---

## 🧪 Results

- Horusec analyzed the source code and reported **vulnerabilities** such as:
  - Hardcoded secrets
  - Missing input validation
  - Use of unsafe functions
- Each finding includes:
  - 📍 File & line number
  - ⚠️ Description of the issue
  - 💡 Recommendation

You can view sample results in the `screenshots/` folder.

---

## 📁 References

- [Horusec CLI Documentation](https://docs.horusec.io/docs/cli/overview/)
- [Juice Shop GitHub](https://github.com/juice-shop/juice-shop)

---

> This demo highlights how easy it is to integrate **SAST scanning** into real-world codebases using open-source tools like Horusec.