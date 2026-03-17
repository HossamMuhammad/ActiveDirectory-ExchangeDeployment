# ActiveDirectory-ExchangeDeployment
Full deployment documentation for Active Directory + Exchange Server on-premises environment
# Active Directory & Exchange Server Deployment (On-Premises)

This repository contains full documentation, scripts, and deployment references for 
implementing an on-premises Active Directory domain and Microsoft Exchange Server environment.

## 📌 Project Overview
- Active Directory Domain Services deployed
- Exchange Server installed and integrated with AD
- Bulk creation of users and mailboxes
- Post-install configurations and cumulative updates
- Automation scripts for user and mailbox provisioning

## 🧱 Technologies Used
- Windows Server 2025
- Active Directory Domain Services
- Exchange Server (CU version)
- PowerShell 5.1
- DNS, DHCP, IIS
- Outlook / Autodiscover

## 📂 Repository Structure
- **architecture/** → diagrams of AD/Exchange topology
- **setup-guides/** → full step-by-step documentation
- **scripts/** → PowerShell scripts used in the deployment
- **csv/** → import templates for users, groups, mailboxes

## 🚀 Deployment Steps (High-Level)
1. Prepare Windows Server environment  
2. Install Active Directory Domain Services  
3. Configure DNS and Sites/Subnets  
4. Prepare Exchange prerequisites  
5. Install Exchange Server & apply Cumulative Update  
6. Configure Virtual Directories, Certificates, Mail Flow  
7. Create Users & Mailboxes (CSV + PowerShell scripts)  
8. Validate deployment with health-check scripts  

## 🧪 Health Checks
Scripts included:
- AD health-check
- Exchange health-check
- Autodiscover and Mailflow tests

## 📝 Author
Hossam Sousi — Voice Expert / Systems Infrastructure  / Microsoft MWP
