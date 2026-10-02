# 🏥 MEDIROZA GENERAL HOSPITAL

*Authorised Penetration Testing*

NetworkWalks Cybersecurity Practical
---
### Assessment Profile

| **Assessment**        | **Details**                                 |
| --------------------- | ------------------------------------------- |
| **Security Tester**   | Kabo Sekoto                                 |
| **Programme**         | NetworkWalks Cybersecurity Practical        |
| **Assessment Type**   | Authorised Web Application Penetration Test |
| **Target**            | Mediroza General Hospital Web Application   |
| **Assessment Period** | September 2026                              |
| **Assessment Phase**  | M1 – M4                                     |
| **Overall Risk**      | 🔴 **CRITICAL**                             |
| **Classification**    | **CONFIDENTIAL**                            |

> **AUTHORISATION:** Testing was performed within an authorised cybersecurity training environment and limited to the approved target.

---


> **Confidential — Authorised Cybersecurity Training Environment**

---

## 🎯 1. Objective

The assessment was conducted to identify and validate security weaknesses within the Mediroza Hospital web application.

### Assessment Focus

* Authentication
* Access control
* SQL injection
* Sensitive document exposure
* PDF password security
* Metadata and information leakage

---

# 🔬2. Methodology

**Reconnaissance → Enumeration → Testing → Validation → Impact Analysis → Reporting**

### Tools Used

`WHOIS` · `DNSRecon` · `NSLookup` · `WhatWeb` · `WAFW00F` · `cURL` · `Nmap` · `Burp Suite` · `John the Ripper / Johnny` · `NetworkWalks`

---

# 🔎 3. M1 — Initial Access

## Reconnaissance

The target was assessed using DNS, web technology, HTTP and network reconnaissance techniques.

```console
kabo@security-lab:~$ whois medirozahospital.com
kabo@security-lab:~$ dnsrecon -d medirozahospital.com
kabo@security-lab:~$ nslookup medirozahospital.com
kabo@security-lab:~$ whatweb https://medirozahospital.com
kabo@security-lab:~$ wafw00f https://medirozahospital.com
kabo@security-lab:~$ curl -I https://medirozahospital.com
```

Nmap and Burp Suite were also used during the assessment.

### Evidence

Only **two representative screenshots** are included for the command-line and application testing activities. The remaining commands were executed and documented but are not individually screenshoted to avoid unnecessary duplication.

![Reconnaissance Commands]()

`[SCREENSHOT 02 — BURP SUITE / APPLICATION TESTING]`

---

## Authentication Testing

Application testing identified an **authentication bypass caused by SQL injection**.

The weakness allowed authentication controls to be bypassed and restricted functionality to be accessed without a valid password.

### Result

🔴 **Authentication Bypass — Validated**

---

# 📄 4. M1 — Document Discovery

Following the authorised access path, three password-protected PDF documents were obtained.

| Target        |   Result   |
| ------------- | :--------: |
| Patient PDF 1 | ✅ Obtained |
| Patient PDF 2 | ✅ Obtained |
| Patient PDF 3 | ✅ Obtained |

**M1 Status:** ✅ **COMPLETE**

---

# 🔐 5. M2 — PDF Password Recovery

## Objective

Assess whether the password protection applied to the recovered PDF documents could be bypassed through offline password recovery.

### Recovery Workflow

**Hash Extraction → John the Ripper / Johnny → NetworkWalks Validation → PDF Access**

### Results

| Target        |   Hash  | Recovery | Validation |
| ------------- | :-----: | :------: | :--------: |
| Patient PDF 1 |    ✅    |     ✅    |      ✅     |
| Patient PDF 2 |    ✅    |     ✅    |      ✅     |
| Patient PDF 3 |    ✅    |     ✅    |      ✅     |
| **Total**     | **3/3** |  **3/3** |   **3/3**  |

### Key Evidence

`[SCREENSHOT 03 — JOHN THE RIPPER / JOHNNY]`

`[SCREENSHOT 04 — VALIDATED PDF ACCESS]`

> John the Ripper / Johnny was used for offline password recovery. NetworkWalks was used to validate successful access to the recovered documents.

**M2 Status:** ✅ **COMPLETE**

---

# 📊 6. M3 — Sensitive Data Exposure

Analysis of the recovered documents identified:

* 🔴 Confidential patient information
* 🔴 Employee salary information
* 🟠 Shareholder information
* 🟠 Sensitive technical information in document metadata

Sensitive personal information should be redacted before public publication.

### Evidence

`[SCREENSHOT 05 — SELECTED SENSITIVE DATA / METADATA EVIDENCE]`

**M3 Status:** ✅ **COMPLETE**

---

# 📸 7. Key Evidence

Evidence is focused on the major findings rather than documenting every command individually.

| ID      | Evidence              | Demonstrates                               |
| ------- | --------------------- | ------------------------------------------ |
| **E01** | Reconnaissance        | Representative command execution           |
| **E02** | Application Testing   | Burp Suite analysis                        |
| **E03** | Authentication Bypass | SQL injection weakness                     |
| **E04** | PDF Recovery          | John the Ripper / Johnny                   |
| **E05** | PDF Validation        | Successful document access                 |
| **E06** | Sensitive Data        | Patient, employee and shareholder exposure |
| **E07** | Metadata              | Technical information leakage              |

> **Evidence principle:** The screenshots demonstrate the key findings. The methodology records the complete set of tools and commands used during the assessment.

---

# 📋 8. Findings Summary

| Finding                                 | Severity    |
| --------------------------------------- | ----------- |
| Authentication bypass via SQL injection | 🔴 Critical |
| Restricted application access           | 🔴 High     |
| Patient documents exposed               | 🔴 Critical |
| PDF passwords recoverable offline       | 🔴 Critical |
| Patient information exposed             | 🔴 Critical |
| Employee salary information exposed     | 🔴 Critical |
| Shareholder information exposed         | 🟠 High     |
| Metadata information leakage            | 🟠 High     |

---

# 🛡️ 9. Recommendations

* Use parameterised SQL queries and prepared statements.
* Strengthen authentication and authorisation controls.
* Apply server-side access control to sensitive documents.
* Store confidential documents securely.
* Use stronger document-password controls.
* Restrict patient, employee and shareholder information.
* Remove unnecessary metadata.
* Monitor authentication and sensitive-document access.
* Perform a security retest after remediation.

---

# 🏁 10. Milestone Completion

| Milestone                           |   Status   |
| ----------------------------------- | :--------: |
| **M1 — Initial Access**             | ✅ Complete |
| **M2 — Data Extraction & Recovery** | ✅ Complete |
| **M3 — Sensitive Data Exposure**    | ✅ Complete |
| **M4 — Professional Report**        | ✅ Complete |

---

# 🔐 11. Conclusion

The authorised assessment identified significant weaknesses in the Mediroza Hospital web application.

Testing demonstrated an authentication bypass, access to restricted functionality, exposure of three protected PDF documents, successful offline password recovery, and exposure of additional sensitive information.

The assessment demonstrates the importance of:

**Secure Authentication → Strong Access Control → Protected Documents → Controlled Metadata → Continuous Security Testing**

---

## ⚠️ Confidentiality Notice

This project was conducted within an **authorised cybersecurity training environment**.

Recovered passwords, credentials and unnecessary patient or personal information must **not** be published in the public repository.

**Learning today. Securing tomorrow.**
