# Unvalidated Redirects and Forwards (Open Redirection Vulnerability)

Unvalidated Redirects and Forwards (Open Redirection) occur when a web application redirects or forwards users to a new URL based on user-controlled input without proper validation [web:22].

---

### Why Redirects Are Necessary [web:25]

*   Redirects help route visitors to different internal or external pages [web:21].
*   They support user flows such as login, registration, and landing pages [web:21].
*   Redirects can point to both internal and external links [web:21].

---

### The Vulnerability [web:25]

*   Attackers exploit the "trust" users have in links provided by a legitimate domain [web:21].
*   When redirects are unvalidated, attackers can manipulate these to send users to malicious external sites [web:21].
*   This can be used for phishing attacks that rely on the perceived trustworthiness of the original domain [web:21].

---

### Security Impact [web:25]

*   Users are deceived into visiting harmful websites [web:21].
*   Leads to theft of credentials, malware installation, and other phishing tactics [web:21].
*   User trust in the affected domain is compromised [web:21].

---

### Mitigation Strategies [web:25]

*   **Do not** use user input directly for redirection URLs [web:25].
*   Validate redirect targets strictly against an allow-list of trusted destinations [web:21].
*   Use server-side mappings for redirect tokens instead of full URLs [web:21].
*   Regularly audit and test applications for open redirect flaws [web:21].
