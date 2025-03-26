# 🧪 SCA Demo - Using Snyk with Juice Shop

This demo replicates the SCA hands-on activity from the **DevSecOps Fundamentals** course using:

- 📦 [OWASP Juice Shop](https://github.com/juice-shop/juice-shop)
- 🔍 [Snyk](https://snyk.io) — a tool for Software Composition Analysis (SCA)

---

## ✅ What was done?

I used **Snyk** to scan the dependencies of Juice Shop’s frontend code and detect known vulnerabilities in third-party libraries.

---

## ⚙️ How to Reproduce

### 1. Clone the vulnerable app

```bash
git clone https://github.com/juice-shop/juice-shop.git
cd juice-shop
npm install
```

### 2. Run Snyk in Docker

Make sure you have a valid `SNYK_TOKEN` exported in your terminal environment:

```bash
docker run --rm -it -e SNYK_TOKEN -v $(pwd):/app snyk/snyk:node
```

---

## 🧪 Results

Snyk scanned **1126 dependencies** and found multiple vulnerabilities, such as:

- 📛 **Critical**: Improper verification of cryptographic signatures (`elliptic`)
- ⚠️ **High**: Insecure randomness, denial of service (DoS), and type confusion
- ⚠️ **Medium**: Resource release issues
- 🔁 Some issues required **upgrading** specific packages (e.g., `ethers`, `socket.io-client`, `@angular-devkit`)
- 🚫 Some vulnerabilities could not be patched directly and required monitoring or changing transitive dependencies

Each issue reported by Snyk included:
- 🔢 Vulnerability ID
- 📄 Description
- 💥 Severity level
- 🔗 Link to full advisory
- 🛠️ Fix recommendation (when available)

---

## 💡 Why this matters

SCA tools like Snyk help identify known vulnerabilities **before deployment**. Even well-known libraries may contain security issues in older versions. Keeping dependencies up to date is a key practice in secure software development.

---

## 🧰 Tools Used

- **Snyk CLI** (Dockerized)
- **Juice Shop** (as vulnerable target app)
- **NPM** (package manager used by the project)

---

## 📂 Files

- This `README.md` — walkthrough and results summary
- `screenshots/` — contains screenshots of the terminal output and snyk example.

---

> 🧠 Even trusted libraries can introduce risk — scan early and often in your pipelines!