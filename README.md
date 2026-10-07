# Web Application Penetration Testing

A structured, practical knowledge base for **web application security testing**, covering penetration testing methodology, web security fundamentals, common vulnerabilities, API security, database concepts, offensive security tools, and hands-on lab references.

> **Purpose:** Maintain organized technical notes for learning, practice, security research, and authorized penetration testing.

---

## Overview

This repository brings together practical notes and references for understanding and assessing web applications from reconnaissance through vulnerability validation.

The content is organized around:

- Web application penetration testing methodology
- Web application labs and practical exercises
- Burp Suite and Intruder
- OWASP Top 10
- Injection vulnerabilities
- Cross-Site Scripting (XSS)
- File Inclusion
- Open Redirect
- SQL Injection
- XML External Entity (XXE)
- Server-Side Request Forgery (SSRF)
- Cross-Site Request Forgery (CSRF)
- Authentication vulnerabilities
- Access Control vulnerabilities
- Session Management
- JSON Web Tokens (JWT)
- HTTP Host Header attacks
- API security
- PHP and MySQL
- Personally Identifiable Information (PII)

---

## Web Application Penetration Testing Lifecycle

The repository includes material related to a practical web application testing workflow:

**Reconnaissance → Application Mapping → Technology Identification → Input Testing → Vulnerability Assessment → Validation → Documentation**

For authorized assessments, the objective is to understand the application attack surface, identify security weaknesses, validate their impact, and document the results clearly.

---

## Repository Structure

### Core Web Application Security

| Topic | Resource |
|---|---|
| Web Application Penetration Testing | [01.Web_application_penetration_testing.md](./01.Web_application_penetration_testing.md) |
| Web Application Labs | [02.Web_Application_Labs.md](./02.Web_Application_Labs.md) |
| PHP Open Source Project | [03.PHP_Open_Source_Project.md](./03.PHP_Open_Source_Project.md) |
| IP Logger | [04.Ip_logger.md](./04.Ip_logger.md) |
| Burp Suite | [05.Burp_Suite.md](./05.Burp_Suite.md) |
| Intruder | [07.Intruder.md](./07.Intruder.md) |
| OWASP Top 10 | [08.OWASP_Top_10.md](./08.OWASP_Top_10.md) |

### HTML Injection

| Topic | Resource |
|---|---|
| HTML Injection | [09.HTML_Injection.md](./09.HTML_Injection.md) |
| HTML Injection with PHP | [10.HTML-injection-2.php.md](./10.HTML-injection-2.php.md) |
| HTML Injection | [11.HTML-injection-3.md](./11.HTML-injection-3.md) |
| Iframe Injection | [12.iframe-injection.md](./12.iframe-injection.md) |
| HTML Injection Reference | [13.Readme_file_html_injection.md](./13.Readme_file_html_injection.md) |

### Cross-Site Scripting (XSS)

| Topic | Resource |
|---|---|
| XSS Injection | [14.XSS-Injection.md](./14.XSS-Injection.md) |
| XSS Injection | [15.XSS_Injection.md](./15.XSS_Injection.md) |
| DOM-Based XSS | [16.Dom-Based-Cross-Site-Scripting.md](./16.Dom-Based-Cross-Site-Scripting.md) |
| Blind XSS & Cross-Site Protection | [17.Blind_XSS_&_Cross_Site_Protection.md](./17.Blind_XSS_&_Cross_Site_Protection.md) |

### Injection & Server-Side Vulnerabilities

| Topic | Resource |
|---|---|
| Code Injection | [18.Code-Injection.md](./18.Code-Injection.md) |
| OS Command Injection | [19.Os_Command_Injection.md](./19.Os_Command_Injection.md) |
| File Inclusion Vulnerability | [20.File-Inclusion-Vulnerability.md](./20.File-Inclusion-Vulnerability.md) |
| Open Redirect | [21.Open-Redirection.md](./21.Open-Redirection.md) |
| SQL Injection | [22.SQL-Injection.md](./22.SQL-Injection.md) |
| XXE | [23.XXE.md](./23.XXE.md) |
| SSRF | [24.SSRF.md](./24.SSRF.md) |
| CSRF | [25.CSRF.md](./25.CSRF.md) |
| SSRF Payloads & Discovery | [26.FInding_SSRF_&_payloads.md](./26.FInding_SSRF_&_payloads.md) |

### Authentication, Authorization & Sessions

| Topic | Resource |
|---|---|
| Authentication Vulnerabilities | [27.Authentication_vulnerabilities.md](./27.Authentication_vulnerabilities.md) |
| Authentication | [28.Authentication_Final.md](./28.Authentication_Final.md) |
| Access Control Vulnerabilities | [29.Access_Control_Vulnerabilities_in_Web_Applications.md](./29.Access_Control_Vulnerabilities_in_Web_Applications.md) |
| Session Management | [30.Session_Management.md](./30.Session_Management.md) |
| JSON Web Tokens (JWT) | [31.JSON_Web_Tokens_(JWT).md](./31.JSON_Web_Tokens_(JWT).md) |
| Cookies, Sessions & Authentication Tokens | [32.Cookies vs Sessions vs Authentication Tokens (JWT).md](./32.Cookies%20vs%20Sessions%20vs%20Authentication%20Tokens%20(JWT).md) |
| HTTP Host Header Attacks | [33.HTTP_Host_Header_Attacks.md](./33.HTTP_Host_Header_Attacks.md) |

### Supporting Security Topics

- Personally Identifiable Information (PII)
- PHP
- MySQL
- API security and testing
- SQL Injection resources
- Practical web application labs

Repository directories:

- [API](./API)
- [MYSQL](./MYSQL)
- [PHP](./PHP)
- [SQL Injection (SQLi)](./SQL%20Injection%20(SQLi))

---

## Tools & Technologies

The repository contains practical references related to tools and technologies used throughout web application security testing, including:

- **Burp Suite**
- **Burp Intruder**
- **Ghauri**
- **PHP**
- **MySQL**
- **HTTP-based web application testing**
- **API testing concepts**
- **OWASP security methodologies**

---

## Key Security Areas

### Application Security
Understanding application functionality, identifying attack surfaces, and testing how the application handles user-controlled input.

### Input Validation
Testing whether application input is properly validated, encoded, filtered, and processed.

### Authentication & Authorization
Assessing login mechanisms, authentication workflows, session handling, access control, and authorization boundaries.

### Injection
Studying injection classes including HTML Injection, XSS, OS Command Injection, SQL Injection, Code Injection, File Inclusion, and XXE.

### Server-Side Request & Application Abuse
Understanding vulnerabilities such as SSRF, open redirect, HTTP Host Header attacks, and related server-side security issues.

### API Security
Organized API-related references covering vulnerable API environments and practical security testing.

---

## Learning Workflow

A practical approach for using this repository is:

**Learn the concept → Understand the attack surface → Test safely → Validate the vulnerability → Assess impact → Document the finding → Retest**

The notes can be used as a reference during authorized labs, security assessments, and personal cybersecurity study.

---

## Recommended Learning Order

For a structured progression:

**1. Web Application Fundamentals**  
Start with web application penetration testing concepts and practical labs.

**2. Reconnaissance & Application Understanding**  
Learn how applications are structured and identify relevant technologies, endpoints, and input points.

**3. Burp Suite**  
Build practical skills with Burp Suite and Intruder for observing and manipulating HTTP requests.

**4. OWASP Top 10**  
Study the major classes of web application vulnerabilities.

**5. Injection Vulnerabilities**  
Progress through HTML Injection, XSS, SQL Injection, Command Injection, Code Injection, File Inclusion, and XXE.

**6. Server-Side Vulnerabilities**  
Study SSRF, open redirect, HTTP Host Header attacks, and related server-side attack surfaces.

**7. Authentication & Access Control**  
Move into authentication weaknesses, access control, sessions, cookies, and JWT.

**8. API & Database Security**  
Continue with API testing, PHP, MySQL, and SQL Injection resources.

---

## Repository Goals

This repository is intended to provide:

- Clear and organized cybersecurity notes
- Practical penetration testing references
- Repeatable testing workflows
- Lab-oriented learning material
- A technical reference for web application security
- Continuous improvement through hands-on practice

---

## Responsible Use

All material in this repository is intended for **educational purposes and authorized security testing**.

Only test applications, systems, APIs, and infrastructure where you have explicit permission to perform security testing. Follow the applicable rules of engagement, organizational policies, and local laws.

---

## Author

**Kartik Yadav**

Cybersecurity | Web Application Security | Penetration Testing

GitHub: [KartikkYadav](https://github.com/KartikkYadav)

---

⭐ This repository is continuously updated with new web application security notes, techniques, tools, and practical learning resources.
