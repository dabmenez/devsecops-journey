# 🔐 Key Security Principles

Understanding key security principles is essential to designing secure systems and applications. Below are foundational concepts used throughout cybersecurity and DevSecOps.

---

## 🧱 Defence in Depth

- **Definition**: A layered security strategy that ensures no single point of failure.
- **Concept**: Instead of relying on one layer (e.g., a password), multiple defenses are put in place.
- **Example**:
  - Strong password policy
  - CAPTCHA after failed login attempts
  - 2FA (Two-Factor Authentication)
  - Geo-location check
  - Email confirmation for logins from unknown locations
- **Goal**: Even if one control fails (e.g., password is compromised), others still protect the system.

---

## 🔐 Least Privilege

- **Definition**: Users, processes, and systems should only have the **minimum access** needed to perform their roles.
- **Example**:
  - A service account doesn't need admin privileges.
  - No shell or interactive login on automated users.
  - Access limited to specific folders or read-only databases.
- **Benefit**: Reduces the attack surface and limits damage from compromised accounts.

---

## 🆔 Authorisation vs Authentication

| Term           | Description |
|----------------|-------------|
| **Authentication** | Verifies **who** you are (e.g., logging in with a password or biometric) |
| **Authorisation**  | Determines **what** you are allowed to do once authenticated |

> 🔒 Just because you're authenticated doesn't mean you're authorized to do everything.

These two work hand in hand:
- **Authentication** confirms identity.
- **Authorisation** enforces limits — helping support least privilege and defence in depth.

---