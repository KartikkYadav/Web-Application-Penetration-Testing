
# 🕷️ Web Application Penetration Testing Cycle (Start → End)
![Penetration Test Phases](https://github.com/user-attachments/assets/b61172fd-4618-442b-a4d6-e4af849b4675)

This document describes the **complete Web Application Penetration Testing lifecycle**, structured using **my personal notes** and enhanced with **industry best practices**.  
It follows a **real-world pentesting workflow** used in professional engagements and bug bounty programs.

---

## 🔵 Phase 0: Pre-Engagement & Legal Formalities
> *Industry Required*

### Objective
Ensure legal authorization and clearly define testing boundaries.

### Includes
- Scope definition (domains, subdomains, URLs)
- In-scope and out-of-scope assets
- Testing type (Black Box / Grey Box / White Box)
- NDA and written authorization
- Bug bounty rules (if applicable)

---

## 🔵 Phase 1: Reconnaissance (Footprinting)
📂 Notes:
- `01.Reconnaissance (Footprinting).md`
- `20.Reconnaissance_CheckList.md`

### Objective
Gather maximum information **without direct interaction**.

### Activities
- Domain and subdomain discovery
- Technology identification
- Hosting and CDN detection
- Publicly exposed assets

---

## 🔵 Phase 2: Spidering & Crawling
📂 Notes:
- `02.Spidering_And_Crawling.md`

### Objective
Map the **entire attack surface**.

### Activities
- Crawl application endpoints
- Identify parameters, forms, and APIs
- Detect hidden paths and features

---

## 🔵 Phase 3: Technology Stack Identification
📂 Notes:
- `03.Built_With.md`
- `05.Content_Delevery_Network_(CDN).md`

### Objective
Understand backend and frontend technologies.

### Identify
- Programming language
- Framework or CMS
- CDN / WAF
- Third-party services

---

## 🔵 Phase 4: Infrastructure-Aware Recon (Web Context Only)
📂 Notes:
- `04.Who_Is_Lookup.md`
- `06.IP_Address_To_Location_Lookup.md`
- `07.ASN_&_Trace_Route.md`

### Objective
Support web testing (not network pentesting).

### Used For
- Ownership and scope validation
- CDN detection
- Origin infrastructure awareness

---

## 🔵 Phase 5: Search Engine & OSINT Recon
📂 Notes:
- `08.Google_Dorks.md`
- `09.Google_Dorking_Cheat_Sheet.md`
- `10.Google_Hacking_Database_Tools.md`
- `11.Github_Recon.md`
- `13.Open_Source_inteligence_(OSINT).md`
- `14.Image_Metadata.md`

### Objective
Discover **exposed data already indexed online**.

### Findings
- Sensitive files
- Admin panels
- API keys
- Credentials
- Old endpoints

---

## 🔵 Phase 6: Email, People & Social Recon
📂 Notes:
- `15.SPF_DKIM_DMARC.md`
- `16.Email_Spoofing.md`
- `17.People_Search_and_OSINT_Tools.md`
- `18.Email_Tracking_And_Protocols.md`
- `19.Gps_Ip_Logger.md`

### Objective
Identify **human and communication weaknesses**.

### Used For
- Phishing simulations
- Account takeover chains
- Password reset abuse

---

## 🔵 Phase 7: Input Validation & Client-Side Testing
📂 Notes:
- `09.HTML_Injection.md`
- `10.HTML-injection-2.php.md`
- `11.HTML-injection-3.md`
- `12.iframe-injection.md`
- `13.Readme_file_html_injection.md`

### Objective
Test how user input is processed and reflected.

---

## 🔵 Phase 8: Cross-Site Scripting (XSS)
📂 Notes:
- `14.XSS-Injection.md`
- `15.XSS_Injection.md`
- `16.Dom-Based-Cross-Site-Scripting.md`
- `17.Blind_XSS_&_Cross_Site_Protection.md`

### Types
- Reflected XSS
- Stored XSS
- DOM-based XSS
- Blind XSS

---

## 🔵 Phase 9: Backend Injection Attacks
📂 Notes:
- `18.Code-Injection.md`
- `19.Os_Command_Injection.md`
- `22.SQL-Injection.md`
- `23.




