# Active Directory & Exchange Server 2019 CU1 Deployment
**Domain:** `hossam.corp`  
**Exchange Version:** Exchange Server 2019 (CU15)  
**Author:** Hossam Sousi  

---

## 📌 Overview
This repository documents the full end-to-end deployment of a complete **Active Directory** and **Microsoft Exchange Server 2019 CU1** environment for the domain **hossam.corp**.

The project includes:
- ADDS installation & configuration  
- Exchange Server 2025 CU15 deployment  
- AD + Exchange integration  
- Bulk user provisioning  
- Bulk mailbox creation  
- Post-installation configuration  
- Health checks and validation scripts  

This documentation follows enterprise best practices and is designed as a technical reference for future deployments, audits, and portfolio showcase.

---

## 🧱 Technologies Used
- **Windows Server 2022** (Domain Controllers)
- **Exchange Server 2019 CU15**
- **Active Directory Domain Services (ADDS)**
- **DNS / Autodiscover / EWS / SMTP**
- **PowerShell 5.1**
- **IIS**
- **.NET Framework dependencies**

---

## 📁 Repository Structure

| Folder | Description |
|--------|-------------|
| `/architecture` | Logical and physical diagrams of AD, Exchange, and mail flow |
| `/setup-guides` | Step-by-step documentation for each stage of deployment |
| `/scripts` | PowerShell automation for AD users, mailboxes, and diagnostics |
| `/csv` | Template CSV files used for bulk provisioning |

---

## 🚀 Deployment Summary (High Level)

### **1. Active Directory Deployment**
- Installed AD Domain Services  
- Promoted server to DC for `hossam.corp`  
- Configured DNS and Sites/Subnets  
- Created OU structure  
- Applied security baselines  

### **2. Exchange 2019 CU15 Installation**
- Installed prerequisites (UCMA, IIS components, .NET)  
- Prepared AD schema using:  
  ```powershell
  Setup.exe /PrepareSchema /IAcceptExchangeServerLicenseTerms
  Setup.exe /PrepareAD /IAcceptExchangeServerLicenseTerms
