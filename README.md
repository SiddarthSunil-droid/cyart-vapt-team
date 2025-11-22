# Week 2 – CYART VAPT Team Labs

This folder contains all artifacts for **Week 2** of the VAPT practice:

1. Vulnerability Scanning Lab  
2. Reconnaissance Practice  
3. Exploitation Lab  
4. Post-Exploitation Practice  
5. Capstone Project: Full VAPT Cycle  

All activities are performed **only in a controlled lab environment** (Kali, Metasploitable2, DVWA, etc.).  
Nothing here should be used against systems without explicit written permission.

---

## Folder Map

- `1-vulnerability-scanning/`
  - `docs/` – PDF report, notes, exported Google Sheet / CSV
  - `screenshots/` – Nmap, OpenVAS, Nikto scan screenshots

- `2-reconnaissance/`
  - `docs/` – Recon report, OSINT notes
  - `screenshots/` – Maltego graphs, Shodan results

- `3-exploitation-lab/`
  - `docs/` – Exploit summary, PoC notes
  - `screenshots/` – Metasploit console, Burp views (lab only)

- `4-post-exploitation/`
  - `docs/` – Meterpreter / Volatility notes, evidence log
  - `screenshots/` – Session info, hashes, memory analysis

- `5-capstone-vapt/`
  - `docs/` – Final PTES report (PDF), non-technical brief, tables
  - `screenshots/` – End-to-end pentest evidence

---

## 1. Vulnerability Scanning Lab

**Tools:** Nmap, OpenVAS, Nikto  
**Target:** Metasploitable2 VM (e.g., `192.168.1.100`) – lab only.

### Workflow Steps

1. **Lab Prep**
   - Ensure Kali and Metasploitable2 are on the same virtual network.
   - Confirm connectivity with a simple ping.

2. **Nmap Service Scan**
   - Run a version detection scan against Metasploitable2 (`-sV`) to identify open ports and services.
   - Save output to a file and take screenshots.
   - Highlight any high-risk services (e.g., outdated web servers, SMB).

3. **OpenVAS Scan**
   - Configure the Metasploitable2 IP as a target in OpenVAS.
   - Launch a full or web-focused vulnerability scan.
   - Export the report (PDF/HTML) to `1-vulnerability-scanning/docs/`.
   - Identify top vulnerabilities with CVSS scores.

4. **Nikto Web Scan**
   - Run Nikto against the Metasploitable2 web service.
   - Note outdated software, dangerous HTTP methods, default files, etc.
   - Save results and screenshots.

5. **Prioritization (CVSS)**
   - In Google Sheets, list key findings with CVSS scores and priorities.
   - Example table (also reusable in Slack):

   ```text
   Scan ID | Vulnerability       | CVSS Score | Priority | Host
   --------|--------------------|-----------|----------|---------------
   001     | SQL Injection      | 9.1       | Critical | 192.168.1.20
   002     | Open Port 445      | 6.5       | Medium   | 192.168.1.30
