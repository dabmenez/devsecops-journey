# OWASP

## 📌 What is it?

OWASP (Open Web Application Security Project) is a **non-profit foundation** whose goal is to improve the security of software.

They maintain **many open-source projects** that help developers, testers, and security engineers better understand and address common security issues.

These projects cover areas such as:
- Tooling
- Testing guides
- Vulnerable software for practice
- Good security practices

---

## 🔧 Projects to Be Familiar With

### 🛠️ OWASP ZAP
- A penetration testing tool (alternative to Burp Suite)
- Supports Windows, Linux, macOS, and Docker
- Works as a **proxy** (man-in-the-middle), intercepting web traffic to identify vulnerabilities
- Can be used through Desktop UI (for pen testers) or Docker (for CI/CD automation)
- Provides alerts and detailed reports of vulnerabilities found

### 🔟 OWASP Top 10
- A document listing the **top 10 most critical web application security risks**
- Updated every few years (last version: 2021)
- Released as PDF

#### 2021 Edition Includes:
1. **Broken Access Control**
2. **Cryptographic Failures**
3. **Injection (e.g., SQL, OS Command)**
4. **Insecure Design**
5. **Security Misconfiguration**
6. **Vulnerable and Outdated Components**
7. **Identification and Authentication Failures**
8. **Software and Data Integrity Failures**
9. **Security Logging and Monitoring Failures**
10. **Server-Side Request Forgery (SSRF)**

### ✅ OWASP ASVS (Application Security Verification Standard)
- Provides a **checklist of security requirements** for web application development
- Useful for both developers and testers
- Available in formats like PDF, Word, CSV

### 📋 OWASP Cheat Sheets
- Concise guides covering specific security topics
- Helps you understand what to do / avoid (e.g., Authentication, Input Validation)
- Maps to OWASP Top 10 and ASVS for easier cross-reference

---

## 🧪 Other Useful OWASP Projects

- **OWASP Juice Shop**: A vulnerable web app for training and testing
- **OWASP ModSecurity Core Rule Set**: Set of rules for ModSecurity WAF
- **OWASP Dependency-Check**: SCA tool to find vulnerable dependencies
- **OWASP Secure Headers Project**: Explains best HTTP security headers
- ...and many more