# Case 001 – Stored XSS in User Registration Form

## 📌 Summary

A **Stored Cross-Site Scripting (XSS)** vulnerability was identified in the user registration flow of a production web application.

User-supplied input was stored and later rendered without proper sanitization, allowing persistent JavaScript execution.

---

## 🛠 Technical Details

* **Vulnerability type:** Stored XSS
* **Attack vector:** User registration form
* **Payload used:** `<script>alert(1)</script>`
* **Trigger:** Automatic execution on page load

---

## ⚠️ Potential Impact

* Persistent JavaScript execution
* Session hijacking
* Phishing via trusted domain
* Impact on privileged users

---

## 🔍 Additional Observations

* Use of outdated frontend dependency: **jQuery 1.9.1**
* Increased risk due to known historical vulnerabilities in legacy libraries

---

## 📊 Severity (CVSS v3.1 – Estimated)

**Base Score:** **8.3 (High)**

**Vector:**

```
CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:C/C:L/I:L/A:N
```

**Metric justification:**

* **AV:N** – Exploitable remotely via web application
* **AC:L** – No special conditions required
* **PR:N** – No authentication required
* **UI:N** – Payload executes automatically once stored
* **S:C** – Impacts user browser context
* **C:L / I:L / A:N** – Limited confidentiality and integrity impact, no availability impact

This score is an estimation provided for learning and portfolio purposes.

---

## ✅ Responsible Disclosure

* Proof of concept limited to `alert(1)`
* No interaction with other users’ data
* Vulnerability privately reported to the organization

---

## 🧠 Lessons Learned

* Stored XSS represents a higher risk than reflected XSS
* Registration flows are high-value targets
* Dependency management is a key part of application security
