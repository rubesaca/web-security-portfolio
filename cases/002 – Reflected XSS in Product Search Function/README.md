# Case 002 – Reflected XSS in Product Search Function

## 📌 Summary

A **Reflected Cross-Site Scripting (XSS)** vulnerability was identified in the product search functionality of a production e-commerce web application.

User-controlled input submitted via the search field was reflected in the response without proper output encoding, allowing execution of arbitrary JavaScript in the browser context.

---

## 🛠 Technical Details

* **Vulnerability type:** Reflected XSS
* **Attack vector:** Product search input
* **Payload used:** `<script>alert(1)</script>`
* **Trigger:** Execution upon search request processing

---

## ⚠️ Potential Impact

* Execution of arbitrary JavaScript in victim browsers
* Session hijacking via crafted links
* Phishing attacks using trusted domain context
* Client-side content manipulation

---

## 🔍 Additional Observations

* Vulnerability exploitable via crafted URLs or social engineering
* Search features are commonly indexed and interacted with, increasing exposure

---

## 📊 Severity (CVSS v3.1 – Estimated)

**Base Score:** **6.1 (Medium)**

**Vector:**

```
CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N
```

**Metric justification:**

* **AV:N** – Exploitable remotely over the web
* **AC:L** – No special exploitation conditions
* **PR:N** – No authentication required
* **UI:R** – User interaction required (clicking crafted link)
* **S:C** – Impacts user browser context
* **C:L / I:L / A:N** – Limited confidentiality and integrity impact

This score is an estimation provided for learning and portfolio purposes.

---

## ✅ Responsible Disclosure

* Proof of concept limited to `alert(1)`
* No access to sensitive data
* Vulnerability reported responsibly to the organization

---

## 🧠 Lessons Learned

* Reflected XSS remains common in search functionalities
* User interaction requirements significantly affect severity scoring
* Proper output encoding is critical even for non-persistent inputs
