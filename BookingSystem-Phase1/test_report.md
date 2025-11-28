# 1️⃣ Introduction

**Tester(s):**  
- Name: Sara Grankvist

**Purpose:**  
- Identify vulnerabilities in the registration flow.

**Scope:**  
- Tested components: Registration flow 
- Exclusions: None
- Test approach: Gray-box

**Test environment & dates:**  
- Start:  21.11.2025
- End: 28.11.2025
- Test environment details:
   - Kali Linux, Linux kernel version 6.16.8 (2025-09-24) (VirtualBox virtual machine, Arch Linux host machine)
   - Docker Engine 29.1.0
   - PostgreSQL 18.0
   - Browsers: Firefox 140.5.0esr, Chromium 142.0.7444.175

**Assumptions & constraints:**  
- Identify issues using given project goals, browser and ZAP
- After issues have been identified, verify through backend as needed (e.g. through postgres console)

---

# 2️⃣ Executive Summary

**Overall risk level:** High

**Top 5 immediate actions:**  
1.  Implement password encryption instead of sending and storing them in plaintext
2.  Add privacy policy and link to it on the registration page
3.  Implement Content Security Policy header
4.  Implement stronger verification for correct email address format
5.  Set password strength requirements

---

# 3️⃣ Severity scale & definitions

|  **Severity Level**  | **Description**                                                                                                              | **Recommended Action**           |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
|      🔴 **High**     | A serious vulnerability that can lead to full system compromise or data breach (e.g., SQL Injection, Remote Code Execution). | *Immediate fix required*         |
|     🟠 **Medium**    | A significant issue that may require specific conditions or user interaction (e.g., XSS, CSRF).                              | *Fix ASAP*                       |
|      🟡 **Low**      | A minor issue or configuration weakness (e.g., server version disclosure).                                                   | *Fix soon*                       |
| 🔵 **Info** | No direct risk, but useful for system hardening (e.g., missing security headers).                                            | *Monitor and fix in maintenance* |


---

# 4️⃣ Findings (filled with examples → replace)

| ID | Severity | Finding | Description | Evidence / Proof |
|------|-----------|----------|--------------|------------------|
| F-01 | 🔴 High | Passwords sent and stored in plaintext | Passwords are sent in plaintext in the POST request, and stored in plaintext in the database | [POST request screenshot](img/credentials-plaintext2.png)<br />[Database screenshot](img/postgres.png) |
| F-02 | 🟠 Medium | Missing privacy policy | Privacy policy link is disabled and the page it points to gives a 404 error | [Page source screenshot](img/gdpr-disabled.png)<br />[404 error screenshot](img/priv404.png) |
| F-03 | 🟠 Medium | Missing Content Security Policy header | Page does not set a CSP header leaving it vulnerable to cross-site-scripting (XSS) attacks | [ZAP report](zap_report_round1.md#content-security-policy-csp-header-not-set)
| F-04 | 🟡 Low | Incomplete email verification | Accepts "addresses" like "aa@aa" | [Database screenshot](img/postgres.png) |
| F-05 | 🟡 Low | Weak password policy | Accepts passwords like "12345" | [Database screenshot](img/postgres2.png) |

# 5️⃣ OWASP ZAP Test Report (Attachment)

**Link to ZAP report**: [ZAP Report](zap_report_round1.md)