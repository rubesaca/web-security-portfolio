# Case 001 – Stored XSS in User Registration Form

## 📌 Summary
A **Stored Cross-Site Scripting (XSS)** vulnerability was identified in the user registration flow of a production web application.

User-supplied input was stored and later rendered without proper sanitization, allowing persistent JavaScript execution.

---

## 🛠 Technical Details
- **Vulnerability type:** Stored XSS
- **Attack vector:** User registration form
- **Payload used:** `<script>alert(1)</script>`
- **Trigger:** Automatic execution on page load

---

## ⚠️ Potential Impact
- Persistent JavaScript execution
- Session hijacking
- Phishing via trusted domain
- Impact on privileged users

---

## 🔍 Additional Observations
- Use of outdated frontend dependency: **jQuery 1.9.1**
- Increased risk due to known historical vulnerabilities in legacy libraries

---

## ✅ Responsible Disclosure
- Proof of concept limited to `alert(1)`
- No interaction with other users’ data
- Vulnerability privately reported to the organization

---

## 🧠 Lessons Learned
- Stored XSS represents a higher risk than reflected XSS
- Registration flows are high-value targets
- Dependency management is a key part of application security

