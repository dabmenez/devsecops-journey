# 🔍 SAST - Static Application Security Testing

## 📌 What is it?

**SAST** stands for **Static Application Security Testing**. It is a type of white-box testing that analyzes an application's **source code**, **bytecode**, or **binary code** to detect **vulnerabilities** before the application is run.

---

## 🧠 Key Characteristics

- **Analyzes code without execution**: SAST reviews the application’s source code to identify **potential security vulnerabilities**.
- **Pinpoints exact location**: It provides the **line(s) of code** where the vulnerability exists, allowing for precise remediation.
- **CI/CD integration**: SAST tools are highly suitable for integration into **CI/CD pipelines**, allowing security checks to run automatically with each commit or build.
- **No downtime required**: Since it doesn't execute the app, SAST does **not impact production or runtime environments**.
- **Detects common issues** like:
  - SQL Injection
  - Buffer Overflows
  - Hardcoded credentials
  - Input validation problems

---

## ⚠️ Limitations

- **Not all issues are detectable**:
  - Can't catch runtime-specific vulnerabilities (e.g. improper authentication, access control flaws).
  - Can't simulate how components interact at runtime.
- **False positives**: SAST tools can produce a **high number of false positives**, requiring manual verification.
- **Doesn’t test the environment** or runtime behavior.

---

## ✅ Summary

| Feature                | Description                                      |
|------------------------|--------------------------------------------------|
| Type                  | Static (white-box) analysis                     |
| Visibility            | Full access to source code                      |
| Ideal for             | Early-stage detection in SDLC                   |
| Pipeline-friendly     | Yes – can be automated and run frequently       |
| Limitations           | Runtime logic, access control, false positives  |

---

> 💡 SAST is most effective when used early in the SDLC to catch coding-level vulnerabilities before they reach production.