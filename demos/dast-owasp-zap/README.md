# 🌐 DAST Demo - Using OWASP ZAP on Juice Shop

This demo replicates the DAST hands-on activity from the **DevSecOps Fundamentals** course using:

- 📦 [OWASP Juice Shop](https://github.com/juice-shop/juice-shop) — a vulnerable application designed for security testing.
- 🛡️ [OWASP ZAP](https://www.zaproxy.org/) — an open-source DAST tool used to find runtime vulnerabilities.

---

## ✅ What was done?

I used OWASP ZAP in a Docker container to scan the running Juice Shop application and identify vulnerabilities. The focus was on observing ZAP’s ability to simulate real-world attacks and report potential security issues.

---

## ⚙️ How to Reproduce

### 1. Start the Juice Shop container

```bash
docker pull bkimminich/juice-shop
docker run --rm -p 127.0.0.1:3000:3000 bkimminich/juice-shop
```

### 2. Run OWASP ZAP against the running app

In another terminal:

```bash
docker run -t ghcr.io/zaproxy/zaproxy:stable zap-baseline.py -t https://www.example.com
```

> 🧠 The baseline scan uses passive scanning and automation rules to quickly identify common web vulnerabilities.

---

## 🧪 Observations

- ZAP scanned **94 URLs** of the running app.
- The majority of tests passed (`PASS`), confirming that many common vulnerabilities were not present or not detectable via passive means.
- A few **warnings** (`WARN-NEW`) were flagged. These include:
  - **Cross-Domain JavaScript Source File Inclusion** `[10017]`
  - **Information Disclosure - Suspicious Comments** `[10027]`
  - **Content Security Policy Header Not Set** `[10038]`
  - **Deprecated Feature Policy Header Set** `[10063]`
  - **Dangerous JS Functions** `[10110]`
  - **Cross-Domain Misconfiguration** `[10098]`

Each warning includes:
- 🔢 The **rule ID**
- 🧠 A brief description of the vulnerability
- 🌐 The affected URL(s)

You can look up each rule ID in the [ZAP Alerts Reference](https://www.zaproxy.org/docs/alerts/) for deeper understanding.

---

## 💡 Why this matters

DAST helps uncover **runtime vulnerabilities** that only appear when the app is live — things like misconfigured headers, exposed secrets in JS, or weak CSP settings. Unlike SAST, it does not analyze the code, but rather **interacts with the app like a real user or attacker would**.

---

## 📂 Files

- `screenshots/` — contains screenshots of the terminal output and ZAP findings.
- This `README.md` — explains the steps, context, and key results.

---

> 🔍 ZAP is a great tool to include in your testing arsenal, especially for APIs and web apps exposed to the public. It's not a replacement for SAST — it's a complement.