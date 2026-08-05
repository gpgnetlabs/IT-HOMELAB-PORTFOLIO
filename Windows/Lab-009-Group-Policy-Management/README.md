# Lab 009 – Group Policy Management

## 📖 Overview

In this lab, I created and deployed a Group Policy Object (GPO) within an Active Directory domain to restrict access to the Windows Control Panel and PC Settings for users in the IT department. After linking the GPO to the appropriate Organizational Unit (OU), I validated that the policy successfully applied to a domain-joined Windows 11 workstation.

---

# 🎯 Objectives

- Create a new Group Policy Object (GPO)
- Configure a User Configuration policy
- Link the GPO to an Organizational Unit
- Verify Group Policy inheritance
- Test policy application on a domain-joined workstation
- Validate the policy using built-in Windows tools

---

# 🏢 Business Scenario

GPG Industries wants to prevent members of the IT department from accessing the Windows Control Panel and PC Settings to reduce unauthorized configuration changes and maintain standardized workstation configurations across the organization.

As the Systems Administrator, I created a Group Policy Object, linked it to the IT Organizational Unit, and verified the policy was enforced on a Windows 11 client joined to the domain.

---

# 🖥️ Lab Environment

**Hypervisor**
- VMware Workstation Pro

**Server**
- Windows Server 2022
- Active Directory Domain Services
- Group Policy Management Console (GPMC)

**Client**
- Windows 11 Pro

**Domain**
```
gpg.local
```

**Domain Controller**
```
GPG-DC01
```

**Client Computer**
```
GPG-VM
```

---

# 🛠️ Technologies Used

- Windows Server 2022
- Windows 11 Pro
- Active Directory Domain Services (AD DS)
- Group Policy Management
- Organizational Units (OUs)
- VMware Workstation Pro
- Command Prompt
- gpresult
- whoami

---

# ⚙️ Implementation

### 1. Created a Group Policy Object

Created a new GPO named:

```
IT Department Restrictions
```

---

### 2. Linked the GPO

Linked the policy to:

```
GPG Industries
└── IT
```

---

### 3. Configured the Policy

Enabled the following policy:

```
User Configuration
└── Policies
    └── Administrative Templates
        └── Control Panel
            └── Prohibit access to Control Panel and PC Settings
```

---

### 4. Updated Group Policy

Logged into the Windows 11 workstation using a domain account and refreshed Group Policy.

---

### 5. Tested the Policy

Attempted to open the Windows Control Panel.

The workstation displayed:

> "This operation has been cancelled due to restrictions in effect on this computer."

confirming the policy was successfully enforced.

---

# 💻 Administrative Tasks / Commands

### Verify domain authentication

```cmd
whoami
```

Expected Output

```text
gpg\sparker
```

---

### Verify applied Group Policies

```cmd
gpresult /r
```

Verified:

- Domain authentication
- Applied GPO
- Domain Controller
- User security groups

---

# ✅ Verification

The following items were successfully verified:

- ✔️ GPO created successfully
- ✔️ GPO linked to the IT Organizational Unit
- ✔️ Windows 11 workstation joined to the domain
- ✔️ Domain user authenticated
- ✔️ Group Policy applied successfully
- ✔️ Control Panel access blocked
- ✔️ gpresult confirmed applied policy
- ✔️ whoami confirmed domain login

---

# 📸 Screenshots

1. Domain Overview
2. GPO Created
3. Organizational Unit Before Linking
4. Group Policy Configuration
5. GPO Linked to IT OU
6. GPO Settings Summary
7. Control Panel Restriction Verified
8. Domain User Authentication (whoami)
9. Applied Group Policy Results (gpresult)
10. Security Groups and Applied Policies

---

# 🧠 Lessons Learned

This lab demonstrated how Group Policy is used to centrally manage user settings across domain-joined computers.

I learned how to:

- Create and configure Group Policy Objects
- Link policies to Organizational Units
- Apply User Configuration policies
- Verify policy deployment using gpresult
- Validate domain authentication using whoami
- Troubleshoot Group Policy deployment

This lab also reinforced the relationship between Active Directory Organizational Units, security groups, and Group Policy Objects.

---

# 💼 Skills Demonstrated

- Active Directory Administration
- Group Policy Management
- Windows Server Administration
- Organizational Unit Management
- Domain Administration
- Endpoint Configuration
- Windows Security
- Group Policy Troubleshooting
- Enterprise User Management
- Command Line Administration

---

# 🚀 Next Lab

**Lab 010 – File Server & Shared Folder Management**

Topics:

- Create shared folders
- Configure NTFS permissions
- Configure Share permissions
- Assign permissions using Active Directory Security Groups
- Test access with different domain users
- Troubleshoot "Access Denied" issues
