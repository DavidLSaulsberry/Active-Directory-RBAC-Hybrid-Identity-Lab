# Active Directory RBAC Home Lab

## Overview

This project demonstrates the design and implementation of an enterprise Active Directory environment for a fictional healthcare organization, **Northstar Medical Group (NMG)**.

The goal of this lab was to rebuild an identity infrastructure using industry-standard Identity and Access Management (IAM) practices, including Organizational Unit (OU) design, Role-Based Access Control (RBAC), user provisioning, PowerShell automation, and incident management through ServiceNow.

The environment simulates responsibilities commonly performed by IAM Analysts, System Administrators, and Help Desk professionals.

---

# Project Objectives

- Build a Windows Server Active Directory domain from scratch
- Create department-based Organizational Units
- Implement Role-Based Access Control (RBAC)
- Provision employee accounts using naming standards
- Automate user creation with PowerShell
- Manage security group assignments
- Troubleshoot Active Directory access issues
- Document incidents using ServiceNow

---

# Environment

| Component | Details |
|---|---|
| Domain | NMG.com |
| Operating System | Windows Server 2022 |
| Directory Service | Active Directory Domain Services |
| Virtualization | VirtualBox |
| Automation | PowerShell |
| Ticketing Platform | ServiceNow |
| Documentation | GitHub |

---

# Active Directory Structure

The Active Directory environment was organized using a department-based OU structure to improve security, administration, and access control.

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
Alejandro Gonzales
agonzales@NMG.com
```

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

# RBAC Implementation

Role-Based Access Control was implemented using Active Directory security groups.

Users were assigned permissions based on department membership rather than individual access assignments.

| Department | Security Group |
|---|---|
| Finance | Finance-Users |
| HR | HR-Users |
| IT | IT-Users |
| Operations | Operations-Users |

This approach improves scalability, security, and simplifies user lifecycle management.

---

# PowerShell User Provisioning Automation

PowerShell was used to automate Active Directory account creation.

Automation included:

- Creating user accounts
- Generating usernames
- Configuring UPNs
- Assigning departments
- Assigning job titles
- Enabling accounts
- Configuring password settings
- Adding users to security groups

This reduced manual provisioning steps and ensured consistent account creation.

---

# ServiceNow Incident Management

A simulated IAM support ticket was created in ServiceNow to replicate a real-world identity issue.

## Incident: INC0010008

### Affected User

Eiona Jackson  
ejackson@NMG.com

### Issue

User reported:

- Unable to access Operations shared resources
- Incorrect mapped drives
- Incorrect desktop policies

### Investigation

The account was found to have:

- Incorrect OU placement
- Incorrect security group membership

### Resolution

Completed actions:

- Moved user account into the Operations OU
- Removed incorrect HR-Users membership
- Added Operations-Users membership
- Verified correct Active Directory configuration
- Documented the resolution

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
│   ├── NMG-0047-Resolution.txt
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
- Identity & Access Management (IAM)
- User Lifecycle Management
- Role-Based Access Control (RBAC)
- Security Group Management
- PowerShell Automation
- ServiceNow Incident Management
- Troubleshooting & Root Cause Analysis
- Technical Documentation

---

# Future Improvements

Future enhancements for this environment include:

- Microsoft Entra ID integration
- Conditional Access policies
- MFA implementation
- Group Policy hardening
- Automated Joiner/Mover/Leaver workflows
- Privileged Access Management integration

---

# Video Walkthrough

Coming Soon

A walkthrough demonstrating:

- Active Directory deployment
- OU structure
- RBAC implementation
- PowerShell automation
- ServiceNow incident resolution

---



**David Saulsberry**

[LinkedIn](https://www.linkedin.com/in/david-saulsberry/) · [GitHub](https://github.com/DavidLSaulsberry)
