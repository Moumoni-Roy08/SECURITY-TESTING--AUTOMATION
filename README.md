# SECURITY TESTING AUTOMATION

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : MOUMONI ROY

*INTERN ID* : CT08MZR

*DOMAIN* : AUTOMATION TESTING

*DURATION* : 4 WEEKS

*MENTOR* :  NEELA SANTOSH



🛡️ Automated Security Testing Report using OWASP ZAP

📌 Task Overview

The objective of this task was to automate security testing for a web application using OWASP ZAP and generate a report detailing identified vulnerabilities and remediation steps. The assessment aimed to detect security weaknesses such as Cross-Site Scripting (XSS), Clickjacking, and CSRF vulnerabilities to enhance application security.


🛠️ Solution

The security test was conducted using OWASP ZAP (Zed Attack Proxy) v2.16.0, an open-source security tool designed for automated vulnerability scanning. The target application for this assessment was http://testphp.vulnweb.com, a purposely vulnerable web application used for penetration testing.

🔄 Workflow:

Target URL Scanned using OWASP ZAP.

Vulnerabilities Identified and categorized by severity.

Security Report Generated with remediation steps.

🛠️ Tools Used

OWASP ZAP v2.16.0 – Automated security scanner.

Target URL: http://testphp.vulnweb.com (Test environment for security testing).

⚠️ Findings and Results

The scan identified 11 vulnerabilities, categorized as follows:

Risk Level	

Number of Issues

🟠 Medium	3
🔵 Low	3
⚪ Informational	5
🔍 Key Vulnerabilities & Fixes
🚨 1. Content Security Policy (CSP) Header Not Set
Risk Level: Medium
Issue: No CSP header, making the app vulnerable to XSS attacks.
Fix: Add the following security header to the web server:
html
Copy
Edit
Content-Security-Policy: default-src 'self';
🚨 2. Missing Anti-Clickjacking Header
Risk Level: Medium
Issue: No X-Frame-Options header, leaving the site open to clickjacking attacks.
Fix: Add this header to prevent embedding in iframes:
html
Copy
Edit
X-Frame-Options: DENY
🚨 3. Absence of Anti-CSRF Tokens
Risk Level: Medium
Issue: Forms lack CSRF protection, making them vulnerable to Cross-Site Request Forgery attacks.
Fix: Include CSRF tokens in form submissions:
html
Copy
Edit
<input type="hidden" name="csrf_token" value="random_token_value">
🚨 4. Server Leaks Version Information
Risk Level: Low
Issue: The server exposes its software version, making it easier for attackers to exploit vulnerabilities.
Fix: Disable version information in server configurations:
bash
Copy
Edit
# Apache
ServerSignature Off
ServerTokens Prod

# Nginx
server_tokens off;
✅ Conclusion
The OWASP ZAP scan successfully identified security vulnerabilities, including missing security headers, lack of CSRF protection, and version disclosure issues.

🛠️ Next Steps
✔️ Implement the recommended security fixes.
✔️ Conduct a follow-up security scan to confirm remediation.
✔️ Regularly update security policies to prevent future threats.

🔐 Security is an ongoing process. Fixing these vulnerabilities will significantly improve application security.

📅 Date: 25/02/2025
🔖 Issued by: [Moumoni Roy]
