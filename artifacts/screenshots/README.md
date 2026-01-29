# Vulnerability Assessment Screenshots

This directory contains visual evidence of the security vulnerabilities discovered during the OWASP Juice Shop assessment.

## Actual Screenshots Captured

### SQL Injection Proof of Concept
- **File:** `Screenshot 2026-01-29 220917.png`
- **Description:** Terminal output showing successful SQL injection attack
- **Evidence:** JWT token and admin user details returned from vulnerable login endpoint

### Information Disclosure Evidence
- **File:** `Screenshot 2026-01-29 220931.png`
- **Description:** Terminal output showing detailed error message with stack trace
- **Evidence:** Application exposing Express.js framework version, file paths, and internal structure

## Vulnerability Evidence Summary

### SQL Injection (CRITICAL)
The first screenshot shows the successful exploitation of the SQL injection vulnerability in the `/rest/user/login` endpoint. The payload `' OR '1'='1'--` bypassed authentication and returned:
- JWT authentication token
- Admin user ID (bid: 1)
- Admin email address (admin@juice-sh.op)

### Information Disclosure (HIGH)
The second screenshot shows the detailed error page generated when sending malformed JSON to the application. This exposes:
- Application framework: Express ^4.21.0
- File system paths: /juice-shop/build/server.js:315:33
- Internal directory structure: /juice-shop/node_modules/
- Complete stack trace with line numbers and function names

## ASCII Art Representations

For reference, this directory also contains ASCII art representations of what Burp Suite screenshots would typically show:
- `sql_injection_visual.txt` - Burp Suite intercept visualization
- `error_disclosure_visual.txt` - Browser error page visualization

## Note
These screenshots provide real visual evidence of the security vulnerabilities discovered during the assessment. Combined with the detailed technical evidence in the `requests/` directory, they form a complete documentation package for the security issues found.
