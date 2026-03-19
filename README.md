# 🔧 Hybrid Active Directory & Microsoft Entra ID Lab (AZ-800)

## 🚀 Overview

Designed and implemented a hybrid identity environment integrating on-prem Active Directory with Microsoft Entra ID.

This lab simulates a real-world enterprise setup, focusing on identity management, policy enforcement, and hybrid infrastructure integration. The environment was built from scratch and includes extensive troubleshooting of common Active Directory and hybrid identity issues.

---

## 🧱 Environment Architecture
<img width="1536" height="1024" alt="System Architecture diagram" src="https://github.com/user-attachments/assets/1fd3d9c1-f828-46a2-b8f3-3d884d3d249b" />

### On-Premises
- **DC01** – Domain Controller (corp.lab)
- **SVR01** – Member Server (Entra Connect, Windows Admin Center)
- **WIN11** – Domain-joined client

### Cloud (Azure)
- Microsoft Entra ID (Azure AD)
- Azure Arc (connected DC01)
- Log Analytics Workspace

---

## 🔧 Core Infrastructure Setup

- Installed and configured Active Directory Domain Services (AD DS)
- Promoted DC01 to Domain Controller for corp.lab
- Configured DNS and verified domain health (dcdiag, repadmin)
- Designed OU structure:
  - Departments → IT / HR / Finance
  - Users / Computers / Groups separation
- Created and managed security groups (IT-Team, HR-Team, Finance-Team)

---

## 🔄 Group Policy & Access Control

- Implemented domain-wide password policy
- Configured desktop and security policies using GPO
- Delegated password reset permissions for HR OU using `dsacls`
- Validated policy application using `gpresult`

---

## 🔁 Hybrid Identity (Entra Connect)

- Installed and configured Microsoft Entra Connect
- Implemented Password Hash Sync
- Configured OU filtering to control sync scope
- Updated UPN suffixes to match Entra ID domain
- Synced on-prem users and groups to Entra ID
- Validated authentication and directory synchronization

---

## ☁️ Azure Integration

- Registered DC01 with Azure Arc
- Configured Log Analytics Workspace
- Explored Azure Monitor data flow:
  - Azure Monitor Agent
  - Data Collection Rules
  - Log Analytics Workspace

---

## 🧪 Troubleshooting & Break-Fix Scenarios

### Domain Controller Issues
- DC02 promotion failures:
  - SID conflicts from cloning
  - Kerberos time synchronization issues
  - Stale AD computer objects

### Group Policy Issues
- GPO not applying due to:
  - Block inheritance
  - Security filtering misconfiguration
  - Incorrect linking

### Identity Sync Challenges
- UPN mismatch issues before Entra Connect
- Sync scope errors due to OU filtering
- Authentication validation after sync

---

## 🛠️ Automation (PowerShell)

- Bulk user creation using CSV import
- Scripted group membership assignment
- Basic administrative task automation

---

## 📸 Screenshots

<img width="1013" height="846" alt="On-prem structure" src="https://github.com/user-attachments/assets/1246ef5d-0b3f-4ad9-ba64-27d6071a6011" />
<img width="1186" height="862" alt="Azure corp lab properties" src="https://github.com/user-attachments/assets/38a79137-0420-465a-950d-84eaab9b9f13" />
<img width="1675" height="551" alt="Azure Arc" src="https://github.com/user-attachments/assets/ab6b453a-ec68-4a45-8049-a3741de5d3d1" />
<img width="1112" height="803" alt="Users" src="https://github.com/user-attachments/assets/f81ae74e-bb2e-4188-b7e2-17ce9fdaf2e5" />


Examples to include:
- AD Users & Computers (OU structure)
- Entra ID synced users
- Azure Arc connected server
- GPO results from client machine

---

## 📚 What This Lab Demonstrates

- Ability to design and deploy Active Directory environments
- Understanding of hybrid identity architecture (on-prem + cloud)
- Hands-on experience with GPOs, delegation, and access control
- Real-world troubleshooting of AD and identity issues
- Familiarity with Azure integration for on-prem systems

---

## 🚧 Next Steps

- Complete multi-DC setup and replication (DC02)
- Expand networking configuration (subnets, routing)
- Implement file services and storage solutions
- Improve PowerShell automation for admin workflows

## ⚠️ Notes

This lab was built in a virtualized environment using VirtualBox.  
Focus was placed on simulating real-world scenarios and troubleshooting failures rather than just completing a clean setup.
