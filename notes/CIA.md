# 🔺 CIA Triad - Core Security Model

The **CIA Triad** represents the three foundational principles of **information security**:

- **C**onfidentiality
- **I**ntegrity
- **A**vailability

These three pillars guide the design, implementation, and evaluation of security systems.

---

## 🔒 Confidentiality

> Ensuring data is **only accessible** by those who are authorized to view it.

- Protects data from **unauthorized access**
- Techniques:
  - Access control (e.g., user roles)
  - Encryption (e.g., file encryption at rest)
  - Multi-factor authentication
  - Network segmentation
- 🧠 Example: Encrypting a file so even if it's leaked, only someone with a key can read it.

---

## 📑 Integrity

> Ensuring data is **accurate and trustworthy**, not tampered with or altered.

- Protects data from **modification** or **corruption**
- Techniques:
  - Hashing (e.g., checksums)
  - Digital signatures
  - Certificates
- 🧠 Example: Verifying a website’s SSL certificate ensures you're really visiting the intended site.

---

## 🟢 Availability

> Ensuring that systems and data are **accessible when needed**.

- Protects against **downtime** and **denial of service**
- Techniques:
  - Redundancy (e.g., failover systems)
  - Load balancing
  - DDoS protection
- 🧠 Example: A website remains online even during traffic spikes due to proper scalability design.

---