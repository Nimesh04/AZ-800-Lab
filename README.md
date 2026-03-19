# Hybrid Active Directory & Microsoft Entra ID Lab (AZ-800)
🚀 Overview
Designed and implemented a hybrid identity environment integrating on-prem Active Directory with Microsoft Entra ID.

This lab simulates a real-world enterprise setup, including domain services, identity synchronization, policy management, and cloud integration.
🧱 Environment Architecture
On-Premises:
- DC01 (Domain Controller – corp.lab)
- SVR01 (Member Server – Entra Connect, Windows Admin Center)
- WIN11 (Domain-joined client)

Cloud:
- Microsoft Entra ID (Azure AD)
- Azure Arc (connected DC01)
- Log Analytics Workspace

👉 YOU NEED TO ADD A DIAGRAM HERE
If you skip this, you’re leaving value on the table.

🔧 Key Features Implemented
- Active Directory Domain Services (AD DS) forest deployment
- OU structure design (Departments: IT, HR, Finance)
- Group Policy Objects (security, desktop, password policies)
- Delegation of control (HR password reset permissions)
- FSMO role management
- AD Recycle Bin enablement and recovery testing
🔄 Hybrid Identity Configuration
- Installed and configured Microsoft Entra Connect
- Implemented Password Hash Sync
- Configured OU filtering for scoped synchronization
- Synced on-prem users and groups to Entra ID
- Validated authentication and identity flow
☁️ Azure Integration
- Registered on-prem DC01 with Azure Arc
- Configured Log Analytics Workspace
- Explored Azure Monitor data collection architecture
🧪 Troubleshooting & Break-Fix Scenarios (THIS IS YOUR GOLD)
- DC02 promotion failures:
  - SID conflicts from cloning
  - Kerberos time synchronization issues
  - Stale AD computer objects

- GPO issues:
  - Block inheritance conflicts
  - Security filtering misconfigurations
  - GPO unlinking and troubleshooting via gpresult

👉 This section is what makes you stand out. Most people don’t have this.

🛠️ Automation (PowerShell)
- Bulk user creation via CSV
- GPO management scripts
- Basic offboarding workflows
