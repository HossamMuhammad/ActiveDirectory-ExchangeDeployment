# Exchange Server On-Prem Deployment

This repository documents the full installation, configuration, and post‑deployment steps for Microsoft Exchange Server on-premises.  
All steps were executed on Windows Server and follow best practices referenced from Ali Tajran’s documentation.

---

## 📌 Environment

- **Windows Server:** 2019 or 2022  
- **Exchange Server:** Exchange 2019 CU (latest available)  
- **Active Directory:** Windows Server 2016+ Forest Functional Level  
- **Server Role:** Mailbox Role (Unified Role)

---

# 1️⃣ Install Windows Server Prerequisites (PowerShell)

## ✔ Install required roles & features

```powershell
Install-WindowsFeature Server-Media-Foundation, FS-FileReplication-Service

Install-WindowsFeature Web-Server, Web-Basic-Auth, Web-Windows-Auth, Web-Metabase, `
Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Filtering, Web-Stat-Compression, `
Web-Dyn-Compression, NET-Framework-45-Features, RPC-over-HTTP-proxy, `
Web-Asp-Net45, WAS-Process-Model, WAS-Config-APIs

---

  # 2️⃣ Install UCMA (Unified Communications Managed API)
Download and install UCMA 4.0 (.exe installer).
(Screen installation — no PowerShell required)

3️⃣ Prepare Active Directory

Run these commands only once per forest.

Navigate to the Exchange setup files:
cd D:\Exchange2019Setup   # Path to Exchange setup media

✔ Prepare Schema

Setup.exe /PrepareSchema /IAcceptExchangeServerLicenseTerms_DiagnosticDataON

✔ Prepare AD
Setup.exe /PrepareAD /OrganizationName:"YourOrg" /IAcceptExchangeServerLicenseTerms_DiagnosticDataON

✔ Prepare Domains
Setup.exe /PrepareAllDomains /IAcceptExchangeServerLicenseTerms_DiagnosticDataON


4️⃣ Install Exchange Server (Mailbox Role)
Setup.exe /Mode:Install /Roles:Mailbox /IAcceptExchangeServerLicenseTerms_DiagnosticDataON

Exchange setup will:

Install mailbox role
Configure services
Create default virtual directories

Since this is Lab environment, i did not install SSL, Connectors. i only added users on Active Directory using powershell to import users from csv file.
i did the same for creating mailboxes for the users.

