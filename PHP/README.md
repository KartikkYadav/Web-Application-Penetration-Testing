# PHP Fundamentals & Web Security

A structured learning and reference section covering **PHP fundamentals, language constructs, data types, variables, arrays, functions, superglobal variables, HTTP concepts, and secure web application headers**.

This directory is part of the [Web-Application-Penetration-Testing](../) repository and provides PHP knowledge that supports web application development, application analysis, and security testing.

---

## Overview

PHP is widely used for server-side web development and is commonly integrated with databases and web servers. This collection organizes practical notes from core PHP concepts through web-focused features such as HTTP request handling, cookies, sessions, file uploads, and security headers.

The material is designed to build a strong foundation before applying PHP knowledge to web application security testing.

---

## Learning Path

**PHP Fundamentals → Data Types → Variables → Arrays → Operators → Loops → Functions → HTTP Input Handling → Superglobals → Sessions & Cookies → File Handling → Secure HTTP Headers**

---

## Contents

### 01. PHP Fundamentals

**[PHP](./01.php.md)**

Introduction to PHP and its role in server-side web development, including:

- Server-side execution
- Dynamic web pages
- HTML integration
- Database interaction
- Forms
- Sessions and cookies
- RESTful APIs
- Basic PHP structure

### 02. Data Types

**[PHP Data Types](./02.Data_Types.md)**

Reference material for understanding PHP data types and how values are represented and handled.

### 03. NULL & Empty Values

**[NULL & Empty](./03.null_empty.md)**

Notes covering NULL and empty-value behavior in PHP.

### 04. Logical Operators

**[Logical Operators](./04.Logical_Operator.md)**

Covers logical operators used to build conditional expressions and control application logic.

### 05. Loops

**[Loops](./05.loops.md)**

Introduces looping constructs used to execute code repeatedly.

### 06. Variables

**[Variables](./06.Variable.md)**

Covers PHP variables and their use throughout application code.

### 07. Arrays

**[Arrays](./07.array.md)**

Reference material for PHP arrays and working with collections of values.

### 08. Array Pointers

**[Pointers in Arrays](./08.pointers_in_array.md)**

Covers array pointer concepts and navigation through array elements.

### 09. Boolean Values

**[Boolean](./09.boolian.md)**

Notes covering Boolean values and true/false evaluation in PHP.

### 10. Functions

**[Functions](./10.functions.md)**

Covers reusable PHP functions, parameters, return values, scope, default parameters, and anonymous functions.

### 11. GET Method

**[GET Method](./11.get_method.md)**

Introduces handling data submitted through HTTP GET requests.

### 12. PHP Superglobal Variables

**[Superglobal Variables](./12.Super-Global-Variable.md)**

Overview of commonly used PHP superglobals, including:

- `$_GET`
- `$_POST`
- `$_REQUEST`
- `$_SERVER`
- `$_SESSION`
- `$_COOKIE`
- `$_FILES`
- `$_GLOBALS`

### 13. Superglobal: `$_GET`

**[Superglobal GET](./13.Super-Global-Get.md)**

Focused reference for retrieving query-string data through the PHP `$_GET` superglobal.

### 14. Superglobal: `$_POST`

**[Superglobal POST](./14.Super_Global_Variable_$_POST.md)**

Notes covering form and request-body data received through HTTP POST requests.

### 15. `$_REQUEST` & `$_SERVER`

**[Request & Server Global Variables](./15.Request_&_Server_Global_Variable.md)**

Covers request data and server/environment information exposed through PHP superglobals.

### 16. `$_FILES`

**[File Global Variable](./16.File_$_Global_Variable.md)**

Reference material for handling uploaded files through PHP's `$_FILES` superglobal.

### 17. `$_COOKIE`

**[Cookie Superglobal Variable](./17.Cookie_Super_Global_Variable.md)**

Covers browser-side cookie data and how PHP reads cookie values.

### 18. `$_SESSION`

**[Session Superglobal Variable](./18.Session_$_Global_Variable.md)**

Introduces server-side session data and its use in maintaining state across requests.

### 19. HTTP Secure Headers

**[HTTP Secure Headers](./19.HTTP-Secure-headers.md)**

Security-focused notes covering HTTP response headers and browser security controls, including:

- Content-Security-Policy (CSP)
- Strict-Transport-Security (HSTS)
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy
- Permissions-Policy
- Cross-Origin-Resource-Policy
- Legacy X-XSS-Protection considerations

---

## Key PHP Concepts

| Area | Focus |
|---|---|
| Fundamentals | PHP syntax, execution, and web integration |
| Data Types | PHP value and type handling |
| Variables | Storing and working with application data |
| Operators | Logical expressions and conditions |
| Loops | Repetitive program execution |
| Arrays | Structured collections of values |
| Functions | Reusable application logic |
| HTTP Input | GET and POST request handling |
| Superglobals | Accessing request, server, session, cookie, and file data |
| Sessions | Maintaining application state |
| Cookies | Client-side stored data |
| File Uploads | Handling uploaded files with `$_FILES` |
| HTTP Security | Browser security and response headers |

---

## PHP in Web Application Security

Understanding PHP internals and request handling is useful when analyzing PHP-based web applications.

The notes in this directory provide foundational knowledge for understanding:

- How applications process user input
- How HTTP request data reaches PHP
- How sessions and cookies maintain application state
- How uploaded files are handled
- How server information is exposed to applications
- How HTTP response headers can improve browser-side security

These concepts connect directly with broader web application security topics covered elsewhere in the parent repository.

---

## Security-Relevant Areas

### Input Handling

PHP applications commonly process data from `$_GET`, `$_POST`, and `$_REQUEST`. Understanding the source and flow of user-controlled data is important when reviewing application behavior.

### Session & Cookie Management

Sessions and cookies are fundamental to authentication and state management. Understanding how these mechanisms work helps with application security analysis.

### File Upload Handling

The `$_FILES` superglobal provides access to information about uploaded files. Secure applications should validate and safely handle uploaded content.

### HTTP Security Headers

Security headers provide browser-level security controls that can help reduce exposure to common web attacks and unsafe browser behavior.

---

## Practical Learning Workflow

A useful progression through this section is:

**Learn PHP basics → Understand application data flow → Practice HTTP input handling → Understand sessions and cookies → Study file handling → Review HTTP security headers → Apply the concepts to web security labs**

---

## Recommended Study Order

For a structured learning experience:

**01 → 02 → 03 → 04 → 05 → 06 → 07 → 08 → 09 → 10 → 11 → 12 → 13 → 14 → 15 → 16 → 17 → 18 → 19**

Start with the PHP language fundamentals and gradually move toward HTTP request handling, superglobals, state management, file handling, and security headers.

---

## Related Topics

This section supports several areas of the parent repository:

- Web Application Penetration Testing
- API Security
- MySQL
- SQL Injection
- Authentication
- Session Management
- File Upload Security
- HTTP Security

**[Back to Web Application Penetration Testing](../)**

---

## Responsible Use

The material is intended for **educational purposes, development practice, and authorized security testing**.

Use security testing techniques only against applications and systems where you have explicit permission to test. Follow applicable laws, organizational policies, and rules of engagement.

---

## Author

**Kartik Yadav**

Cybersecurity | Web Application Security | Penetration Testing

GitHub: [KartikkYadav](https://github.com/KartikkYadav)

---

⭐ This section is continuously updated with PHP fundamentals, web development concepts, and security-focused learning material.
