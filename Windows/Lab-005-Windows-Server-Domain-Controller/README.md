# Lab 005 – Windows Server 2022 Domain Controller Deployment

## Objective

Deploy a Windows Server 2022 Domain Controller by installing Active Directory Domain Services (AD DS), configuring DNS, assigning a static IP address, and creating a new Active Directory forest for a simulated enterprise environment.

---

## Skills Demonstrated

- Windows Server Administration
- Active Directory Domain Services (AD DS)
- Domain Controller Deployment
- DNS Configuration
- Static IPv4 Configuration
- Server Management
- Active Directory Forest Creation
- VMware Virtualization
- Enterprise Network Planning

---

## Environment

| Component | Value |
|-----------|-------|
| Hypervisor | VMware Workstation |
| Server OS | Windows Server 2022 Standard Evaluation |
| Computer Name | GPG-DC01 |
| Domain | gpg.local |
| Forest | gpg.local |
| IP Address | 192.168.177.10 |
| Default Gateway | 192.168.177.2 |
| Preferred DNS | 192.168.177.10 |
| Alternate DNS | 192.168.177.2 |

---

## Business Scenario

A new company, **GPG Industries**, requires an on-premises Active Directory environment to centrally manage users, computers, groups, security policies, and authentication.

As the Systems Administrator, I deployed the organization's first Domain Controller and created a new Active Directory forest to serve as the foundation of the enterprise network.

---

## Implementation

### Step 1 – Install Windows Server 2022

- Installed Windows Server 2022 Standard Evaluation
- Completed initial configuration
- Verified network connectivity

---

### Step 2 – Rename the Server

Changed the default hostname to:

```

GPG-DC01

```

Restarted the server.

---

### Step 3 – Configure Static IPv4

Configured:

- IP Address: 192.168.177.10
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.177.2
- Preferred DNS: 192.168.177.10
- Alternate DNS: 192.168.177.2

---

### Step 4 – Install Active Directory Domain Services

Installed:

- Active Directory Domain Services (AD DS)

Included management tools and PowerShell modules.

---

### Step 5 – Promote Server to Domain Controller

Created:

- New Forest

Forest Name:

```

gpg.local

```

Configured:

- DNS Server
- Global Catalog
- DSRM Password

---

### Step 6 – Complete Installation

Verified prerequisite checks.

Completed promotion.

Server automatically rebooted.

---

### Step 7 – Verify Deployment

Confirmed:

- Domain Controller operational
- DNS installed
- Active Directory Users and Computers available
- Successfully logged in using the domain Administrator account

---

## Commands Used

```powershell
hostname

ipconfig /all

Get-ADDomain

Get-ADForest

Get-Service DNS

Get-Service NTDS
```

---

## Verification

Successfully verified:

- Domain Controller operational
- DNS functioning
- Active Directory accessible
- Forest created
- Domain created
- Administrator authentication successful

---

## Technologies Used

- Windows Server 2022
- Active Directory Domain Services
- DNS
- VMware Workstation
- TCP/IP
- IPv4
- Microsoft Management Console
- PowerShell

---

## Screenshots

1. Server Manager Dashboard
2. Local Server Properties
3. Static IP Configuration
4. AD DS Installation Wizard
5. Promote Server to Domain Controller
6. New Forest (gpg.local)
7. Prerequisite Check
8. Successful Installation
9. Domain Administrator Login
10. Active Directory Users and Computers
11. DNS Manager

---

## Lessons Learned

- Domain Controllers require a static IP address.
- Active Directory relies heavily on DNS.
- Promoting a server installs the Active Directory database.
- A forest is the highest-level logical structure in Active Directory.
- Windows Server Manager greatly simplifies role deployment.

---

## Skills for Employers

This lab demonstrates experience with:

- Windows Server Administration
- Active Directory
- DNS
- Domain Controller Deployment
- Enterprise Authentication
- Microsoft Server Infrastructure
- VMware Virtualization
- Systems Administration
