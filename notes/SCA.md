# 🧩 SCA - Software Composition Analysis

## 📌 What is SCA?

**SCA** stands for **Software Composition Analysis**. It refers to the process of analyzing an application’s **third-party dependencies** to identify known vulnerabilities, outdated components, and licensing issues.

Modern applications rarely run in isolation — they rely heavily on **external libraries** and **frameworks**, which themselves may have dependencies. These are usually defined in files like `package.json`, `pom.xml`, or `requirements.txt`.

---

## 🔍 Example

Consider a `package.json` like this:

```json
"dependencies": {
  "array-flatten": "1.1.1",
  "node-emoji": "1.0.0"
}
```

This means:
- `node-emoji@1.0.0` may depend on:
  - `lodash@1.0.0`
  - `methods@1.0.0`

This creates a **dependency tree**, which can grow large and complex. SCA tools map this tree and check each component for vulnerabilities.

---

## 🧪 What Does SCA Do?

SCA tools scan your dependency list to:
- Determine which components you're using (including transitive dependencies).
- Check if any are:
  - **Outdated**
  - **Known to be vulnerable (linked to CVEs)**
- Recommend updates or patches to secure your software.

---

## 🔗 How it works

- It operates similarly to **SAST**, since it analyzes files statically.
- It integrates well with **CI/CD pipelines** to run automatically on each build.
- It relies on **open vulnerability databases** like the NVD (National Vulnerability Database).

---

## ⚠️ Why it matters

Using old versions of common libraries can put your app at risk.

For example:
> You might be using `lodash@1.0.0`, and an SCA tool could alert that this version is vulnerable to **multiple CVEs**, recommending an upgrade to a safer version.

---

## 🧰 SCA Tools

Some popular open-source and commercial tools for SCA include:

- **OWASP Dependency-Check**
- **Snyk**
- **WhiteSource (now Mend)**
- **GitHub Dependabot**
- **Trivy**
- **Sonatype Nexus**

---

## ✅ Summary

| Feature               | Description                                             |
|------------------------|---------------------------------------------------------|
| What it scans         | Dependency files (e.g., `package.json`)                 |
| Purpose               | Detect outdated/vulnerable libraries                    |
| Scan type             | Static (white-box)                                      |
| CI/CD ready?          | ✅ Yes                                                  |
| Risk detected         | Known CVEs, outdated versions, license issues           |
| Complements           | SAST and DAST (focuses on 3rd-party components)          |

---

> 💡 Keeping your dependencies updated is one of the simplest yet most effective ways to secure your application early in the SDLC.