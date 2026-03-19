# 🔧 Hybrid Active Directory & Microsoft Entra ID Lab (AZ-800)

## 🚀 Overview

Designed and implemented a hybrid identity environment integrating on-prem Active Directory with Microsoft Entra ID.

This lab simulates a real-world enterprise setup, focusing on identity management, policy enforcement, and hybrid infrastructure integration. The environment was built from scratch and includes extensive troubleshooting of common Active Directory and hybrid identity issues.

---

## 🧱 Environment Architecture

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

*(Add images in /screenshots folder and reference them here)*

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

---

## 📂 Repository Structure
