# CTF Training

<div align="center">

<img src="Images/kali-linux.png" width="720" alt="Kali Linux">

<br><br>

<img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white"/>
<img src="https://img.shields.io/badge/Burp%20Suite-F47B20?style=for-the-badge&logo=burpsuite&logoColor=white"/>
<img src="https://img.shields.io/badge/Web%20Security-PortSwigger-red?style=for-the-badge"/>
<img src="https://img.shields.io/badge/CTF-Learning-success?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Status-In%20Progress-blue?style=for-the-badge"/>

<br><br>

**A hands-on Cyber Security & CTF learning journey — from Linux fundamentals to web exploitation.**

</div>

---

<p align="center">
  <img src="Images/burpsuite.png" width="720" alt="Burp Suite">
</p>

---

## About

This repository documents my personal journey into **Cyber Security**, **Web Application Security**, and **Capture The Flag (CTF)** challenges.

My focus is on **practical understanding** — not memorizing payloads or copying write-ups. Every topic is explored through hands-on labs, real traffic analysis, and detailed documentation.

**Topics I'm covering:**

- Linux Fundamentals
- Networking & Protocols
- HTTP Protocol Deep Dive
- Web Security Vulnerabilities
- Penetration Testing Methodologies
- CTF Problem-Solving

---

## Learning Roadmap

Here's what I've accomplished and what's coming next:

| Phase | Topic | Status |
| :---: | ----- | :----: |
| 01 | Linux Fundamentals | ✅ |
| 02 | Networking Fundamentals | ⏳ |
| 03 | HTTP Protocol | ✅ |
| 04 | Burp Suite | ✅ |
| 05 | Cookies & Sessions | ✅ |
| 06 | SQL Injection | ⏳ |
| 07 | Cross-Site Scripting (XSS) | ⏳ |
| 08 | Authentication | ⏳ |
| 09 | Access Control (IDOR) | ⏳ |
| 10 | File Upload Vulnerabilities | ⏳ |
| 11 | Command Injection | ⏳ |
| 12 | Path Traversal | ⏳ |
| 13 | Server-Side Request Forgery (SSRF) | ⏳ |
| 14 | XML External Entity (XXE) | ⏳ |
| 15 | Cross-Site Request Forgery (CSRF) | ⏳ |
| 16 | JWT & OAuth | ⏳ |
| 17 | API Security | ⏳ |
| 18 | Enumeration (Nmap, ffuf, Gobuster) | ⏳ |
| 19 | Privilege Escalation | ⏳ |
| 20 | CTF Practice | ⏳ |

---

## Repository Structure

```text
.
├── README.md                    # This file — overview of the journey
├── Linux.md                     # Linux fundamentals: commands, permissions, package management
├── BurpSuite.md                 # Burp Suite setup and workflow
└── Images/                      # Screenshots from labs and tools
    ├── kali-linux.png
    ├── burpsuite.png
    └── sql-injection.png
```

Each Markdown file contains:
- **Concise theory** — what you need to know before starting.
- **Step-by-step walkthroughs** — how I performed each exercise.
- **Screenshots** — visual references and proof of progress.
- **Key takeaways** — what I learned and how to apply it.

---

## Current Lab

<p align="center">
  <a href="https://portswigger.net/web-security/sql-injection/lab-login-bypass">
    <img src="Images/sql-injection.png" width="720" alt="SQL Injection Lab">
  </a>
</p>

**Objective:** SQL Injection — Authentication Bypass

This lab is part of the **PortSwigger Web Security Academy** and is designed to demonstrate how improper input handling can lead to authentication bypass.

**Lab URL:**  
https://portswigger.net/web-security/sql-injection/lab-login-bypass

---

## Environment

| Component | Technology |
| --------- | ---------- |
| Operating System | Kali Linux 2026.1 |
| Virtual Machine | VirtualBox 7.x |
| Browser | Firefox |
| Proxy | Burp Suite Community Edition |
| Learning Platform | PortSwigger Web Security Academy |

---

## Learning Philosophy

> **Understand first. Exploit second. Memorize never.**

My workflow:

1. Learn the theory.
2. Understand how it works.
3. Observe HTTP traffic.
4. Practice in a controlled lab.
5. Document everything.
6. Review and refine.

---

## Disclaimer

This repository is intended **strictly for educational purposes**.

All exercises are performed on intentionally vulnerable systems like **PortSwigger Web Security Academy**.

The techniques documented here must never be used against systems without explicit permission.

---

<div align="center">

**Stay curious. Stay ethical. Keep learning.**

</div>