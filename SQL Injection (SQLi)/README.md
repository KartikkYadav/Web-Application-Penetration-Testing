# SQL Injection (SQLi)

A structured, practical reference for understanding, testing, and documenting **SQL Injection vulnerabilities** in web applications.

This section is part of the [Web-Application-Penetration-Testing](../) repository and focuses on SQL injection concepts, injection techniques, database enumeration, blind SQL injection, authentication-related SQLi scenarios, and common SQL injection testing tools.

---

## Overview

SQL Injection occurs when untrusted application input is incorporated into database queries without appropriate protection. This collection is organized as a practical learning path covering SQL injection fundamentals, different injection types, database structure discovery, error-based and blind techniques, authentication bypass scenarios, out-of-band and second-order concepts, and automated testing tools.

The material is intended to help build a strong understanding of how SQL injection works and how it can be assessed safely in authorized lab and testing environments.

---

## Learning Path

**SQLi Fundamentals → Injection Types → Parameter Analysis → Database Enumeration → Error-Based SQLi → Blind SQLi → Authentication Testing → Data Extraction Concepts → Advanced SQLi → Automation & Tooling**

---

## Contents

### 01. SQL Injection Fundamentals

**[SQL Injection (SQLi)](./01.%20SQL%20Injection%20(SQLi).md)**

Introduction to SQL injection, the basic vulnerability concept, and how unsafe application input can affect backend database queries.

### 02. Types of SQL Injection

**[Types of SQL Injections](./02.Types%20of%20SQL%20Injections%20.md)**

Covers different SQL injection categories and their general characteristics.

### 03. ID Parameter Behavior

**[ID Parameter Behavior](./03.id%20Parameter%20Behavior.md)**

Practical notes for analyzing application parameters and identifying database-backed behavior.

### 04. Using Information Schema

**[Information Schema for SQL Injection](./04.Using%20information_schema%20for%20SQL%20Injection.md)**

Covers the use of database metadata and `information_schema` during authorized SQL injection testing and database structure discovery.

### 05. Error-Based SQL Injection

**[Error-Based Basic Injection](./05.Error-based%20Basic%20Injection.md)**

Introduces error-based SQL injection and the use of database errors as a source of useful testing information.

### 06. Query Techniques

**[Break, JOIN, ORDER BY & UNION Query](./06.break,%20join%20,order%20by%20,union%20%20query.md)**

Reference material covering SQL query structures relevant to SQL injection testing, including JOIN, ORDER BY, and UNION-based concepts.

### 07. Database Enumeration

**[Database Enumeration](./07.Database%20-Enumeration.md)**

Organized notes on identifying database structure and enumerating available database information during testing.

### 08. Error-Based SQLi Payloads

**[Payloads for Error-Based SQL Injection](./08.%20Payloads%20for%20error-based%20SQL%20injection%20.md)**

Reference material for error-based SQL injection testing and payload concepts used in controlled environments.

### 09. Double Query Injection

**[Double Query Injection (DQI)](./09.Double-Query-Injection%20(DQI).md)**

Detailed notes on double-query injection techniques and their behavior.

### 10. Error-Based SQLi – Version-Specific Techniques

**[New Version Error-Based SQLi](./10.new%20version%20error%20based%20%20%202,3,4,5%206.md)**

Version-oriented notes covering error-based SQL injection techniques and related database behavior.

### 11. Error-Based SQLi with POST Requests

**[Error-Based SQLi – POST Request Method](./11.error%20based%20%20post%20request%20method.md)**

Covers SQL injection testing in HTTP POST request parameters and form-based application workflows.

### 12. Blind SQL Injection Commands

**[SQL Commands Used in Blind SQL Injection](./12.%20SQL-Commands-Used-in-Blind-SQL-Injection.md)**

Reference material for SQL statements and concepts used when working with blind SQL injection scenarios.

### 13. Boolean-Based SQL Injection Practice

**[Boolean-Based SQL Injection Practice](./13.sql%20command%20injection%20praticle%20%20in%20bollen%20based%20in%20web.md)**

Practical notes focused on boolean-based SQL injection behavior in web applications.

### 14. Time-Based Blind SQL Injection

**[Time-Based Blind SQL Injection](./14.%20Time-based%20Blind%20SQL%20Injection.md)**

Covers time-based blind SQL injection concepts where differences in application response time can provide a testing signal.

### 15. Authentication Bypass Lab

**[Authentication Bypass – SQL Injection Lab](./15.login%20n%20(Authentication%20Bypass%20%E2%80%93%20SQL%20Injection%20Lab).md)**

Hands-on laboratory material focused on authentication-related SQL injection scenarios.

### 16. Authentication Bypass Payload Reference

**[Authentication Bypass Payloads](./16.authentication%20bypass-payloads-sql-injection%20all%20in%20one.md)**

A consolidated reference for authentication-bypass SQL injection payload concepts used in controlled lab environments.

### 17. Data Extraction & Dumping

**[Dumping Data with SQL Injection](./17.dumping-data-injection.md)**

Notes covering data extraction concepts and database content retrieval during authorized SQL injection testing.

### 18. Out-of-Band SQL Injection

**[Out-of-Band SQL Injection (OOB SQLi)](./18.%20Out-of-Band-SQL-Injection-(OOB-SQLi).md)**

Introduces out-of-band SQL injection concepts, where external interaction can be used as a signal during testing.

### 19. Second-Order SQL Injection

**[Second-Order SQL Injection](./19.second%20order%20%20sql%20%20injection%20.md)**

Covers second-order SQL injection scenarios where stored input is later processed in a vulnerable database operation.

### 20. SQLMap

**[SQLMap](./20.Sqlmap.md)**

Notes covering SQLMap, a widely used tool for automating SQL injection detection and exploitation in authorized environments.

### 21. SQLMap with POST Requests

**[SQLMap – POST Request Testing](./21.sql%20map%20tool%20post%20request.md)**

Reference material for using SQLMap with HTTP POST request data in controlled assessments.

### 22. Ghauri

**[Ghauri](./22.Ghauri%20online%20password%20cracking%20tool.md)**

Reference notes covering Ghauri for SQL injection testing and automation.

---

## SQL Injection Categories Covered

| Category | Coverage |
|---|---|
| Basic SQL Injection | Fundamentals and parameter behavior |
| Error-Based SQLi | Error-driven testing and payloads |
| UNION-Based SQLi | Query manipulation and result combination concepts |
| Boolean-Based SQLi | True/false response analysis |
| Time-Based Blind SQLi | Response timing analysis |
| Authentication Bypass | Login and authentication workflows |
| Database Enumeration | Schema and database metadata discovery |
| Data Extraction | Retrieving database information during authorized testing |
| Out-of-Band SQLi | External interaction-based testing |
| Second-Order SQLi | Stored input triggering later SQL execution |
| Automated SQLi | SQLMap and Ghauri |

---

## Core Testing Areas

### Parameter Analysis

Identify application inputs that may interact with database queries, including:

- URL parameters
- Form fields
- JSON parameters
- POST request data
- Identifiers such as `id`
- Authentication inputs

### Database Enumeration

Understand database structure and metadata, including:

- Databases
- Tables
- Columns
- Relationships
- Database version information
- Metadata available through database schemas

### Error-Based Testing

Review application and database responses for useful error information that may reveal query structure or database behavior.

### Blind SQL Injection

When query results are not directly displayed, evaluate application behavior through:

- Boolean conditions
- Response differences
- Timing behavior

### Authentication Testing

Review login and authentication workflows for SQL injection conditions that could affect authentication logic.

### Advanced SQL Injection

The collection also covers:

- Double-query injection
- Out-of-band SQL injection
- Second-order SQL injection
- Advanced error-based techniques

---

## Tools Referenced

### SQLMap

Automates many SQL injection testing tasks and supports multiple request and database scenarios.

### Ghauri

An automated SQL injection testing tool referenced in the collection for controlled security assessments.

### Burp Suite

Useful for intercepting, modifying, and replaying HTTP requests while testing application parameters.

### cURL

Useful for sending and reproducing HTTP requests during manual API and web testing.

---

## Practical Testing Workflow

A structured SQL injection assessment can follow this sequence:

**1. Identify Inputs**  
Map parameters, forms, JSON fields, and request data that interact with backend functionality.

**2. Understand Application Behavior**  
Establish normal responses before making controlled changes to parameters.

**3. Test for Injection Indicators**  
Evaluate whether application behavior changes unexpectedly when input is modified.

**4. Identify the Injection Context**  
Determine how the application processes the input and what type of SQL injection may be applicable.

**5. Enumerate Database Information**  
Where authorized and appropriate, determine database type, version, schema, tables, and columns.

**6. Validate Impact**  
Confirm the security impact using the minimum necessary proof of concept.

**7. Document the Finding**  
Record the affected parameter, endpoint, evidence, impact, root cause, severity, and remediation.

**8. Retest After Remediation**  
Verify that the underlying issue has been properly fixed.

---

## Defensive Considerations

The strongest defense against SQL injection is to ensure user-controlled input is never treated as executable SQL syntax.

Common defensive practices include:

- Parameterized queries / prepared statements
- Safe ORM usage
- Strict input validation where appropriate
- Least-privilege database accounts
- Secure error handling
- Avoiding dynamic SQL where unnecessary
- Regular security testing and code review
- Monitoring for abnormal database query behavior

---

## Common SQLi Indicators During Testing

Potential indicators can include:

- Database error messages
- Unexpected response changes
- Different results for logically related inputs
- Application response timing differences
- Unexpected authentication behavior
- Exposed database metadata
- Query-related server errors

An indicator alone is not sufficient to establish a vulnerability; findings should be reproducible and validated within the authorized test scope.

---

## Recommended Study Order

For a structured progression:

**01 → 02 → 03 → 04 → 05 → 06 → 07 → 08 → 09 → 10 → 11 → 12 → 13 → 14 → 15 → 16 → 17 → 18 → 19 → 20 → 21 → 22**

Start with SQL injection fundamentals and parameter behavior, then progress through database enumeration, error-based and blind techniques, authentication testing, advanced SQL injection concepts, and automation tools.

---

## Related Sections

This SQL Injection section connects directly with other areas of the parent repository:

- [Web Application Penetration Testing](../)
- [MySQL](../MYSQL)
- [PHP](../PHP)
- [API Security](../API)

Understanding SQL and relational databases is especially useful when assessing database-backed web applications and APIs.

---

## Responsible Use

All content is intended for **educational purposes and authorized security testing**.

Use SQL injection testing techniques only against applications and systems where you have explicit permission to conduct security testing. Use the included vulnerable labs and examples in controlled environments.

---

## Author

**Kartik Yadav**

Cybersecurity | Web Application Security | Penetration Testing

GitHub: [KartikkYadav](https://github.com/KartikkYadav)

---

⭐ This section is continuously updated with SQL injection notes, testing methodologies, lab exercises, and security tooling references.
