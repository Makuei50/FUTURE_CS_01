# FUTURE_CS_01
# Altoro Mutual - Vulnerability Assessment & Security Audit

# Project Overview
I conducted a comprehensive automated and manual security assessment against the Altoro Mutual banking web application simulation. The primary objective of this audit was to map the network attack surface, intercept application-layer traffic, and identify critical security configuration gaps, missing browser defenses, and infrastructure exposures.

# Tested Website
* **Target Application:** Altoro Mutual
* **Application Type:** Corporate Banking Web Simulation
* **Testing Environment:** Sandbox / Isolated Security Lab

# Scope of Assessment
The evaluation focused on two main defensive layers to determine how vulnerable the application is to exploitation:

1.  **Network Layer Footprinting:** * Scanning infrastructure endpoints to locate open ports, discover active services, and map daemon software versions.
    * Evaluating infrastructure information disclosure vectors.
2.  **Application Layer Configurations (Data Transit & Defensive Headers):**
    * Analyzing connection transport security protocols (HTTP vs. HTTPS).
    * Auditing the existence, strength, and configurations of client-side browser guardrails (HTTP Response Headers).
    * Assessing session management safety, cookie flags, and cross-site scripting (XSS) script-loading directives.

# Tools Used

During this audit, I deployed industry-standard security tools to gather passive and active intelligence:

* **Zenmap / Nmap:** Used for network layer discovery, port scanning, and service version enumeration to map out the baseline attack surface.
* **OWASP ZAP (Zed Attack Proxy):** Utilized as an intercepting proxy to perform passive analysis of HTTP requests and response headers, uncovering 30 distinct system-layer alerts.
* **Browser Developer Tools:** Deployed for direct inspecting of the Document Object Model (DOM), Network tab response tracking, and evaluating session cookie properties.

# Key Findings Summary
* **Insecure Transit:** The application communicates over unencrypted HTTP instead of secure HTTPS, exposing traffic to potential plaintext interception.
* **Missing Defensive Headers:** Systemic absence of foundational server security headers including `Strict-Transport-Security` (HSTS), `X-Frame-Options` (Anti-Clickjacking), and a robust `Content-Security-Policy` (CSP).
* **Exposed Session Management:** Session cookies were observed lacking vital `HttpOnly` and `Secure` defensive flags, risking credential theft through client-side scripting or local network sniffing.

*This repository serves as a technical portfolio project demonstrating vulnerability discovery, tool-based auditing methodology, and defensive infrastructure remediation.*
