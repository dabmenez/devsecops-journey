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



### 📊 Scan Summary

After running Horusec against the Juice Shop's frontend code, the tool identified a **large number of vulnerabilities**. These were automatically classified by severity levels — such as **critical**, **high**, and **medium** — helping prioritize which issues should be addressed first.

Most of the findings were classified as **critical**, indicating serious issues in the source code that could pose significant risks if left unresolved. This demonstrates how valuable SAST tools like Horusec are when integrated early in the development cycle, allowing teams to catch vulnerabilities before they ever reach production.

The tool also highlights exactly **where** in the code the issues are located, what kind of issue it is (e.g., hardcoded credentials, lack of input validation), and even suggests remediation actions. This makes it easier to take immediate and informed action on improving code security.


Below is the output from the terminal after running Horusec:

```
In this analysis, a total of 238 possible vulnerabilities were found and we classified them into:
Total of Vulnerability CRITICAL is: 206
Total of Vulnerability HIGH is: 30
Total of Vulnerability MEDIUM is: 2
```

You can view sample results in the `screenshots/`.
---

## 📁 References

- [Horusec CLI Documentation](https://docs.horusec.io/docs/cli/overview/)
- [Juice Shop GitHub](https://github.com/juice-shop/juice-shop)

---

> This demo highlights how easy it is to integrate **SAST scanning** into real-world codebases using open-source tools like Horusec.