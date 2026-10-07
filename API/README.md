# API Security & Penetration Testing

A practical API security knowledge base covering **API fundamentals, security considerations, OWASP API Security Top 10, penetration testing methodology, authorization testing, authentication weaknesses, data exposure, rate limiting, and vulnerable API labs**.

This section is part of the [Web-Application-Penetration-Testing](../) repository and is focused specifically on understanding and assessing modern APIs in authorized testing environments.

---

## Overview

APIs are a core component of modern web, mobile, and microservice applications. This collection provides structured notes for understanding how APIs work and how to assess common security weaknesses across authentication, authorization, input handling, business logic, and data exposure.

The material progresses from API fundamentals to hands-on security testing and intentionally vulnerable platforms such as **crAPI** and **VAmPI**.

---

## Learning Path

**API Fundamentals → API Architecture → Security Considerations → OWASP API Security Top 10 → Lab Setup → Testing Methodology → Vulnerability Testing → Practical Labs**

---

## Contents

### 01. API Fundamentals

**[Application Programming Interface (API)](./01.%20Application_Programming_Interface_(API)..md)**

Covers API fundamentals, including:

- API concepts and purpose
- Endpoints
- HTTP methods
- Request and response structure
- HTTP status codes
- Common API use cases
- Authentication mechanisms
- API-based applications vs. traditional web applications

### 02. API Security Considerations

**[API Security Considerations](./02.API_Security_Considerations.md)**

Focuses on security risks commonly encountered during API assessments:

- Broken Object Level Authorization (BOLA)
- Broken Authentication
- Mass Assignment
- Rate Limiting issues
- Excessive Data Exposure
- CORS misconfiguration
- Injection risks
- API objects and actions
- REST and action-based endpoints

### 03. What is an API?

**[What is API](./03.What%20is%20API.md)**

Additional API fundamentals and terminology for building a strong foundation before moving into security testing.

### 04. Types of API

**[Types of API](./04.Types%20of%20API.md)**

Reference material covering different API types and their characteristics.

### 05. OWASP API Security Top 10

**[OWASP API Security Top 10](./05.OWASP-API-Security-Top-10.md)**

Security reference based on the **OWASP API Security Top 10 (2023)**, including topics such as:

- Broken Object Level Authorization
- Broken Authentication
- Broken Object Property Level Authorization
- Unrestricted Resource Consumption
- Broken Function Level Authorization
- Unrestricted Access to Sensitive Business Flows
- Server-Side Request Forgery
- Security Misconfiguration
- Improper Inventory Management
- Unsafe Consumption of APIs

### 06. Lab Setup

**[API Lab Setup](./07.Lab-Setup.md)**

Environment setup and supporting material for practicing API security testing in controlled lab environments.

### 07. API Penetration Testing Methodology

**[API Penetration Testing Methodology](./08.API%20Penetration%20Testing%20Methodology.md)**

A structured testing workflow covering:

1. Reconnaissance and API discovery
2. API documentation discovery
3. Traffic analysis
4. Authentication analysis
5. Authorization testing
6. Endpoint enumeration
7. HTTP method testing
8. Input validation
9. Injection testing
10. Business logic testing
11. Rate limiting and brute-force testing
12. Data exposure analysis
13. Configuration and security review
14. Reporting and validation

### 08. crAPI Testing

**[crAPI Testing](./09.crAPI_Testing.md)**

Hands-on practice against **crAPI (Completely Ridiculous API)**, an intentionally vulnerable application designed around API security weaknesses.

Topics include:

- BOLA
- Broken User Authentication
- Excessive Data Exposure
- Rate Limiting
- Broken Function Level Authorization
- Mass Assignment
- Business logic abuse

### 09. Broken Object Level Authorization (BOLA)

**[BOLA](./10.Broken%20Object%20Level%20Authorization%20(BOLA).md)**

Detailed study of object-level authorization weaknesses, including testing API object identifiers, access control failures, impact, root cause, and remediation.

### 10. Broken User Authentication

**[Broken User Authentication](./11.Broken_User_Authentication.md)**

Covers weaknesses in authentication and password recovery workflows, including OTP validation and account takeover scenarios in the documented lab environment.

### 11. Excessive Data Exposure

**[Excessive Data Exposure](./12.%20Excessive%20Data%20Exposure.md)**

Covers API responses that expose more information than required, including:

- Sensitive fields
- Internal identifiers
- Debug information
- Tokens and credentials
- Improper response filtering

### 12. Broken Function Level Authorization (BFLA)

**[BFLA](./13.Broken%20Function%20Level%20Authorization%20(BFLA))**

Covers authorization failures where users can access functionality intended for higher-privileged roles, along with rate-limiting considerations documented in the same study material.

### 13. VAmPI Testing

**[VAmPI Testing](./14.vampi_testimg.md)**

Practical API security testing using **VAmPI**, with examples covering:

- BOLA
- JWT weaknesses
- Mass Assignment
- Excessive Data Exposure
- Rate Limiting
- Injection testing
- Authorization testing

### 14. Vulnerable E-Commerce API Platform

**[Vulnerable E-Commerce API Platform](./15.Vulnerable%20E-Commerce%20API%20Platform.md)**

A deliberately vulnerable e-commerce API lab designed for security training and penetration testing practice.

The documented platform includes functionality such as:

- JWT authentication and authorization
- Product catalog management
- Shopping cart operations
- Order processing
- Reviews and ratings
- Admin functionality
- File uploads
- Internal service simulation
- Webhooks
- Coupon and discount workflows

---

## Key Security Domains

| Security Domain | Focus |
|---|---|
| API Fundamentals | Endpoints, methods, requests, responses, status codes |
| Authentication | Sessions, JWT, API keys, OAuth, mTLS |
| Authorization | BOLA, BFLA, privilege boundaries |
| Input Validation | SQLi, NoSQLi, command injection, JSON manipulation |
| Data Exposure | Sensitive fields, debug data, excessive responses |
| Business Logic | Workflow abuse, replay, race conditions, transaction manipulation |
| Rate Limiting | Brute force, OTP abuse, resource exhaustion |
| Configuration | CORS, documentation exposure, API inventory |
| API Discovery | Swagger, OpenAPI, GraphQL, Postman collections |

---

## Tools Referenced

The notes in this section reference tools commonly used for API security testing and analysis:

- **Burp Suite**
- **Postman**
- **cURL**
- **FFUF**
- **mitmproxy**
- **JWT Editor**
- **Swagger UI**
- **OWASP ZAP**

---

## Practical Testing Workflow

A professional API assessment can be approached using the following sequence:

**1. Discover the API**  
Identify base URLs, versions, documentation, endpoints, and exposed specifications.

**2. Understand Requests and Responses**  
Review methods, parameters, headers, cookies, tokens, request bodies, and response data.

**3. Analyze Authentication**  
Identify the authentication mechanism and review token handling, expiration, and validation.

**4. Test Authorization**  
Assess horizontal and vertical access controls, including object- and function-level authorization.

**5. Test Input Handling**  
Assess parameters and JSON structures for injection and unexpected property handling.

**6. Test Business Logic**  
Review workflows for abuse, replay, manipulation, and missing controls.

**7. Test Resource Controls**  
Assess rate limiting, payload restrictions, and protection against excessive requests.

**8. Analyze Data Exposure**  
Look for unnecessary sensitive information, debug data, and internal properties in responses.

**9. Document Findings**  
Record evidence, affected endpoints, security impact, root cause, severity, and remediation.

---

## Lab Environments

The repository includes practical material for intentionally vulnerable API environments, including:

- **crAPI**
- **VAmPI**
- **Vulnerable E-Commerce API**

These environments are intended to provide controlled practice for understanding API security weaknesses and validating defensive concepts.

---

## Recommended Study Order

For the most structured progression:

**01 → 02 → 03 → 04 → 05 → 07 → 08 → 09 → 10 → 11 → 12 → 13 → 14 → 15**

Start with API fundamentals, then move through security principles and OWASP risks before progressing into methodology and vulnerable application labs.

---

## Responsible Use

All content in this directory is intended for **educational purposes and authorized security testing**.

Use the techniques only against APIs, applications, and systems where you have explicit permission to perform security testing. Do not use intentionally vulnerable applications or security techniques against production systems or third-party infrastructure without authorization.

---

## Related Repository

Parent repository:

**[Web-Application-Penetration-Testing](../)**

This API section is part of a broader collection covering web application penetration testing and application security.

---

## Author

**Kartik Yadav**

Cybersecurity | API Security | Web Application Security | Penetration Testing

GitHub: [KartikkYadav](https://github.com/KartikkYadav)

---

⭐ This section is continuously updated with API security notes, testing methodologies, vulnerable lab references, and practical penetration testing knowledge.
