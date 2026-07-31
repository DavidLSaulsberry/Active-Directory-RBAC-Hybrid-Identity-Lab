# Active Directory RBAC + Microsoft Entra ID Hybrid Identity Home Lab

# Overview

This project demonstrates the design and implementation of a hybrid Identity and Access Management (IAM) environment for a fictional healthcare organization, **Northstar Medical Group (NMG)**.

The goal of this lab was to build an enterprise-style identity infrastructure using **Active Directory Domain Services (AD DS)** integrated with **Microsoft Entra ID** through **Azure AD Connect**.

The environment demonstrates real-world IAM concepts including:

- Organizational Unit (OU) design
- Role-Based Access Control (RBAC)
- User provisioning
- Identity lifecycle management
- Hybrid identity synchronization
- Multi-Factor Authentication (MFA)
- PowerShell automation
- Incident management through ServiceNow

This lab simulates responsibilities commonly performed by **IAM Analysts, Identity Engineers, System Administrators, and Help Desk professionals**.

---

# Project Objectives

- Build a Windows Server Active Directory domain from scratch
- Design department-based Organizational Units (OUs)
- Implement Role-Based Access Control (RBAC)
- Create and manage employee identities
- Automate account provisioning using PowerShell
- Configure Active Directory security groups
- Integrate Active Directory with Microsoft Entra ID
- Configure Azure AD Connect synchronization
- Implement MFA using Microsoft Authenticator
- Troubleshoot identity and access issues
- Document incidents using ServiceNow

---

# Environment

| Component | Details |
|---|---|
| Domain | NMG.com |
| Operating System | Windows Server 2022 |
| Directory Service | Active Directory Domain Services |
| Cloud Identity Provider | Microsoft Entra ID |
| Identity Synchronization | Azure AD Connect |
| Virtualization | VirtualBox |
| Automation | PowerShell |
| Authentication Security | Microsoft Authenticator MFA |
| Ticketing Platform | ServiceNow |
| Documentation | GitHub |

---

# Hybrid Identity Architecture

The environment was configured as a hybrid identity solution by connecting an on-premises Active Directory environment with Microsoft Entra ID.

Azure AD Connect was used to synchronize identities between Active Directory and Microsoft Entra ID.

The following identity objects were synchronized:

- User accounts
- User Principal Names (UPNs)
- Security groups
- User attributes

Architecture:

```
On-Premises Environment

Active Directory Domain Services
              |
              |
       Azure AD Connect
              |
              |
     Microsoft Entra ID
              |
              |
     Cloud Applications
```

This setup simulates how organizations maintain both on-premises and cloud identity environments.

---

# Active Directory Structure

The Active Directory environment was organized using department-based Organizational Units to improve administration, security, and access control.

```
NMG.com
│
├── Finance OU
│   └── Finance-Users
│
├── HR OU
│   └── HR-Users
│
├── IT OU
│   └── IT-Users
│
└── Operations OU
    └── Operations-Users
```

---

# User Provisioning

A total of **15 employee accounts** were created following standardized identity naming conventions.

Username format:

```
First Initial + Last Name
```

Example:

```
Employee:
Alejandro Gonzales

Username:
agonzales

UPN:
agonzales@NMG.com
```

Each account was configured with:

- First and last name attributes
- Department information
- Job title
- User Principal Name (UPN)
- Security group membership
- Password settings
- Enabled account status

---

# Employee Accounts

## Finance Users

| Name | Username | Role |
|---|---|---|
| Alejandro Gonzales | agonzales | Finance Manager |
| Chase Colbert | ccolbert | Finance Analyst |
| Collin McGee | cmcgee | Payroll Specialist |
| Aryan Luitel | aluitel | Accounts Payable Specialist |

## HR Users

| Name | Username | Role |
|---|---|---|
| Antonio Adams | aadams | HR Manager |
| Saige Burgan | sburgan | HR Recruiter |
| Ron Spidell | rspidell | Benefits Coordinator |

## IT Users

| Name | Username | Role |
|---|---|---|
| Kyle Dwyer | kdwyer | IT Administrator |
| Edward Hull | ehull | Security Analyst |
| Brianne Young | byoung | Help Desk Technician |
| Evan Yearwood | eyearwood | Systems Engineer |

## Operations Users

| Name | Username | Role |
|---|---|---|
| Yazide Chitou | ychitou | Operations Manager |
| Eiona Jackson | ejackson | Operations Coordinator |
| Tchai Chambers | tchambers | Facilities Supervisor |
| Keshawn Lynch | klynch | Scheduling Coordinator |

---

# Role-Based Access Control (RBAC)

RBAC was implemented using Active Directory security groups.

Users were assigned permissions based on their department and job responsibilities instead of assigning permissions individually.

| Department | Security Group |
|---|---|
| Finance | Finance-Users |
| HR | HR-Users |
| IT | IT-Users |
| Operations | Operations-Users |

Benefits of this RBAC approach:

- Improved security
- Simplified permission management
- Easier onboarding and offboarding
- Supports scalable identity lifecycle management
- Follows least privilege principles

---

# Microsoft Entra ID Integration

Microsoft Entra ID was integrated with the Active Directory environment to create a hybrid identity solution.

Azure AD Connect was configured to synchronize:

- Active Directory users
- Security groups
- Identity attributes
- User Principal Names (UPNs)

Users created in Active Directory were synchronized into Microsoft Entra ID, allowing cloud-based identity management.

This demonstrated how enterprise organizations manage identities across both on-premises and cloud environments.

---

# Multi-Factor Authentication (MFA)

MFA was enabled using **Microsoft Authenticator** to strengthen authentication security.

Users were required to complete additional verification during login.

Authentication workflow:

```
User Sign-In

      ↓

Username + Password

      ↓

Microsoft Authenticator Approval

      ↓

Access Granted
```

Security benefits:

- Reduces risk from compromised passwords
- Provides stronger identity verification
- Supports Zero Trust security principles
- Improves account protection

---

# PowerShell User Provisioning Automation

PowerShell was used to automate Active Directory account creation and management.

Automation included:

- Creating user accounts
- Generating usernames
- Configuring UPNs
- Assigning departments
- Assigning job titles
- Enabling accounts
- Configuring passwords
- Adding users to security groups

Automation improved consistency, reduced manual work, and followed standardized provisioning practices.

---

# ServiceNow Incident Management

A simulated IAM support ticket was created in ServiceNow to replicate a real-world identity issue.

## Incident: INC0010008

### Affected User

**Eiona Jackson**

Username:

```
ejackson@NMG.com
```

---

## Issue

The user reported:

- Unable to access Operations shared resources
- Incorrect mapped drives
- Incorrect desktop policies

---

## Investigation

The account was discovered to have:

- Incorrect Organizational Unit placement
- Incorrect security group membership

---

## Resolution

Completed actions:

- Moved user account into the Operations OU
- Removed incorrect HR-Users membership
- Added Operations-Users membership
- Verified Active Directory configuration
- Confirmed correct permissions
- Documented resolution in ServiceNow

---

# Repository Structure

```
Active-Directory-RBAC-Home-Lab
│
├── Documentation
│   ├── Domain Config File
│   ├── Security Group Documentation
│   ├── User List Documentation
│   └── RBAC-Structure.md
│
├── Incident-Reports
│   ├── INC0010008-Resolution.txt
│   └── ServiceNow-Ticket.png
│
├── Screenshots
│   ├── Day1
│   ├── Day2
│   ├── Day3
│   └── Day4
│
└── README.md
```

---

# Skills Demonstrated

- Active Directory Administration
- Microsoft Entra ID
- Hybrid Identity Management
- Azure AD Connect
- Identity Synchronization
- Identity Lifecycle Management
- Role-Based Access Control (RBAC)
- User Provisioning
- Security Group Management
- Multi-Factor Authentication (MFA)
- Microsoft Authenticator
- PowerShell Automation
- ServiceNow Incident Management
- Troubleshooting
- Root Cause Analysis
- Technical Documentation

---

# Future Improvements

Future enhancements for this environment include:

- Conditional Access policies
- Passwordless authentication
- Privileged Access Management (PAM)
- CyberArk integration
- Automated Joiner/Mover/Leaver workflows
- Group Policy security hardening
- Entra ID Governance
- Access Reviews
- Separation of Duties (SoD)
- Identity Governance workflows

---

# Video Walkthrough

https://youtu.be/6Whn4dQBcMs
---



**David Saulsberry**

[LinkedIn](https://www.linkedin.com/in/david-saulsberry/) · [GitHub](https://github.com/DavidLSaulsberry)
