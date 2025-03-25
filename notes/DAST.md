# 🔍 DAST - Dynamic Application Security Testing

## 📌 What is DAST?

**DAST** stands for **Dynamic Application Security Testing**. Unlike SAST, which analyzes code before execution, DAST focuses on **testing a running application** by interacting with it through its **UI or API** to find vulnerabilities.

It is considered a form of **black-box testing**, meaning it doesn't have access to the source code — it only sees what an external attacker could see when interacting with the application.

---

## 🧪 Key Characteristics

- Tests a live application during runtime.
- Can identify vulnerabilities such as:
  - **SQL injection**
  - **Buffer overflows**
  - **Cross-site scripting (XSS)**
  - **Authentication flaws**
- It simulates real-world attacks and observes the application's responses.
- Best suited for **post-build testing** or **penetration testing phases**.
- **Can** be added to CI/CD pipelines, but is **mostly used manually** or in dedicated test environments.

---

## ⚫ Black-box Testing

DAST tools operate with no knowledge of the internal structure of the application. This approach:
- Mimics how an attacker would explore the system.
- Is limited to what's exposed externally (e.g., it can't "see" hardcoded secrets or logic hidden in the backend).
- Complements SAST (white-box) to provide a broader view of security posture.

---

## 🧰 Tools & Automation

There are many DAST tools available, but several important points include:

- **Many DAST tools are commercial** and more oriented toward manual testing than automation.
- Automation is possible, but integration with pipelines is less common and often more complex.
- Popular tools include:
  - 🔓 **[OWASP ZAP](https://www.zaproxy.org/)** (open-source)
  - 💼 **Burp Suite** (widely used in industry, but has a paid version)

---

## ✅ When to Use DAST

| Use Case                             | Recommended |
|-------------------------------------|-------------|
| Testing API/Frontend vulnerabilities| ✅           |
| Simulating attacker behavior        | ✅           |
| Catching runtime issues             | ✅           |
| Scanning code before build          | ❌ (Use SAST)|
| Automated checks in CI/CD           | ⚠️ (Possible but not ideal) |

---

> 💡 Use DAST alongside SAST for a more complete security testing strategy. SAST checks the code internally, while DAST checks the behavior externally.
