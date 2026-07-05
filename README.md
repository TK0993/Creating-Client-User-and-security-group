# Active Directory & Identity Management Home Lab Portfolio



An enterprise-grade documentation portfolio demonstrating the deployment, configuration, and management of **Active Directory Domain Services (AD DS)**, **Group Policy Objects (GPOs)**, and core operational infrastructure features within a simulated Managed Service Provider (MSP) environment on **Windows Server 2022**.



This project provides tangible, hands-on verification of baseline IT administration skills, multi-tenant directory architecture, role-based access control (RBAC), automated system configuration, and business continuity readiness.



---



## 🛠️ Core Technologies & Environments

* **Operating System:** Windows Server 2022 Datacenter Edition (Core & Desktop Experience)

* **Hypervisor:** Oracle VirtualBox

* **Automation Framework:** Windows PowerShell 5.1

* **Management Frameworks:** Active Directory Users and Computers (`dsa.msc`), Group Policy Management Console (`gpmc.msc`), Windows Server Backup (`wbadmin.msc`), and Windows Server Update Services (`wsus.msc`).



---



## 🏗️ Project Architecture & Walkthrough



### Part 1: Identity & Access Management (AD DS)



In a Managed Service Provider (MSP) infrastructure, maintaining absolute isolation and clean classification across multiple corporate client systems is crucial. This section details the multi-tenant directory layout built to manage identities securely.



#### 1. Organizational Unit (OU) Creation

Instead of populating the default containers, a dedicated Organizational Unit named `MockClientA` was generated. This acts as a logical security boundary for client-specific policies and access rules.

```powershell

# Conceptual background deployment

New-ADOrganizationalUnit -Name "MockClientA" -Path "DC=trustlab,DC=local" -ProtectedFromAccidentalDeletion $true
