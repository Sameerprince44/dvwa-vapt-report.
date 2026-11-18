# DVWA Web Application Vulnerability Assessment

A hands-on penetration testing project conducted against **Damn Vulnerable Web Application (DVWA)**, a deliberately vulnerable PHP/MySQL web app used for security training. This project simulates a real-world VAPT (Vulnerability Assessment and Penetration Testing) engagement in an isolated lab environment.

## 📋 Overview

- **Target:** DVWA v1.10 (Low security level)
- **Environment:** Kali Linux VM, DVWA deployed via Docker
- **Methodology:** OWASP Top 10
- **Findings:** 8 vulnerabilities (3 Critical, 3 High, 2 Medium)

## 🛠 Tools Used

- **Nmap** — reconnaissance and service enumeration
- **Burp Suite (Community)** — proxying, request interception, automated attacks (Intruder)
- Manual payload crafting and exploitation

## 🔍 Findings

| # | Vulnerability | Severity | Location |
|---|---|---|---|
| 1 | SQL Injection | Critical | `/vulnerabilities/sqli/` |
| 2 | Unrestricted File Upload → RCE | Critical | `/vulnerabilities/upload/` |
| 3 | Command Injection | Critical | `/vulnerabilities/exec/` |
| 4 | Local File Inclusion (LFI) | High | `/vulnerabilities/fi/` |
| 5 | Stored XSS | High | `/vulnerabilities/xss_s/` |
| 6 | CSRF | Medium-High | `/vulnerabilities/csrf/` |
| 7 | Reflected XSS | Medium-High | `/vulnerabilities/xss_r/` |
| 8 | Brute Force (no lockout) | Medium | `/vulnerabilities/brute/` |

Full details for each finding — including steps to reproduce, impact, and remediation — are in [`Web Application Vulnerability Assessment Report.pdf`](./Web%20Application%20Vulnerability%20Assessment%20Report.pdf).

## 📸 Proof of Concept

Screenshots for each finding are in the [`/screenshots`](./screenshots) folder, including:
- SQL injection dumping user credentials
- Uploaded PHP web shell achieving remote code execution
- Command injection returning `www-data`
- `/etc/passwd` read via Local File Inclusion
- Stored and Reflected XSS payloads executing
- CSRF password-change request with no token
- Burp Intruder brute-force attack results

## 🎯 Key Takeaways

This project involved setting up a full testing lab from scratch (VirtualBox, Kali Linux, Docker, Burp Suite), manually identifying and exploiting 8 distinct vulnerability classes, and writing a professional-style security assessment report with severity ratings and remediation guidance for each finding — mirroring the deliverables expected in an entry-level penetration testing or SOC analyst role.

## ⚠️ Disclaimer

This assessment was performed exclusively against DVWA running in a local, isolated lab environment for educational purposes. No systems outside of this controlled environment were tested or accessed.

## 📬 Contact

**Shaik Sameer**
sameerprince44p@gmail.com
