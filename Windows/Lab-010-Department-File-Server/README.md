# Lab 010 – Department File Server & NTFS Permissions

## 📖 Overview

In this lab, I configured a Windows Server file server by creating departmental shared folders for Accounting, HR, and IT. I implemented both Share Permissions and NTFS Permissions using Active Directory security groups to enforce role-based access control (RBAC). I then verified access from a domain-joined Windows 11 client to ensure users could only access resources assigned to their department.

---

## 🎯 Objectives

- Create departmental file shares
- Configure SMB sharing
- Configure Share Permissions
- Configure NTFS Permissions
- Assign access using Active Directory Security Groups
- Verify user access from a domain-joined workstation
- Validate successful access and denied access scenarios

---

## 🏢 Business Scenario

GPG Industries is expanding its internal network infrastructure and requires a centralized file server to securely store departmental documents.

Each department should have its own shared folder that is only accessible by authorized employees:

- Accounting employees should only access the Accounting share.
- HR employees should only access the HR share.
- IT employees should only access the IT share.

Access control is managed through Active Directory Security Groups following the Principle of Least Privilege.

---

## 🖥️ Lab Environment

**Server**

- Windows Server 2022
- Active Directory Domain Services
- Domain: `gpg.local`

**Client**

- Windows 11 Pro
- Domain Joined
- Logged in using domain user accounts

**Virtualization**

- VMware Workstation Pro

---

## 🛠️ Technologies Used

- Windows Server 2022
- Windows 11 Pro
- Active Directory Users and Computers
- SMB File Sharing
- NTFS Permissions
- Active Directory Security Groups
- Computer Management
- File Explorer
- Windows Networking

---

## ⚙️ Implementation

### Step 1

Created a centralized folder named:

```
C:\CompanyShares
```

Inside the folder, created three departmental folders:

- Accounting
- HR
- IT

---

### Step 2

Enabled SMB Sharing for each folder using Advanced Sharing.

Created the following network shares:

- Accounting
- HR
- IT

---

### Step 3

Verified all shares were successfully published using Computer Management.

Confirmed:

- Accounting
- HR
- IT

appeared under Shared Folders.

---

### Step 4

Configured NTFS Permissions.

Disabled inheritance and converted inherited permissions into explicit permissions.

Removed unnecessary default permissions while keeping:

- SYSTEM
- Administrators
- CREATOR OWNER

---

### Step 5

Assigned department-specific security groups with **Modify** permissions.

| Folder | Security Group |
|---------|----------------|
| Accounting | Accounting |
| HR | HR |
| IT | IT_Admins |

This implemented Role-Based Access Control (RBAC).

---

### Step 6

Logged into a Windows 11 domain workstation using department user accounts.

Verified:

- Authorized users successfully accessed their assigned share.
- Unauthorized users received **Access Denied**.

---

## 💻 Administrative Tasks / Commands

### Network Share

```
\\GPG-DC01
```

or

```
\\192.168.177.10
```

### Verify Logged-in User

```cmd
whoami
```

### Verify Applied Group Policy

```cmd
gpresult /r
```

---

## ✅ Verification

Successfully verified:

✅ Department folders created

✅ SMB shares published

✅ Share permissions configured

✅ NTFS permissions configured

✅ Active Directory Security Groups assigned

✅ Domain user authentication successful

✅ Authorized users accessed assigned shares

✅ Unauthorized users received Access Denied

---

## 📸 Screenshots

1. Company Shares Folder Created
2. Accounting Share Enabled
3. Share Permissions
4. Shared Folders Console
5. Accounting NTFS Before Configuration
6. Selecting Accounting Security Group
7. Accounting NTFS Permissions Configured
8. IT NTFS Permissions Configured
9. HR NTFS Permissions Configured
10. Access Denied Verification
11. Successful IT Share Access

---

## 🧠 Lessons Learned

This lab demonstrated how Share Permissions and NTFS Permissions work together to secure shared resources.

I learned that:

- Share permissions control network-level access.
- NTFS permissions control file system access.
- NTFS permissions provide the primary layer of security in enterprise Windows environments.
- Active Directory Security Groups simplify permission management and improve scalability.
- Testing with actual domain users is essential to verify access behaves as expected.

I also gained practical experience implementing the Principle of Least Privilege using role-based access control.

---

## 💼 Skills Demonstrated

- Windows Server Administration
- Active Directory Administration
- SMB File Sharing
- NTFS Permissions
- Share Permissions
- Active Directory Security Groups
- Role-Based Access Control (RBAC)
- Windows Networking
- Domain Authentication
- Access Control Verification
- Windows Troubleshooting

---

## 🚀 Next Lab

**Lab 011 – Group Policy Drive Mapping**

In the next lab, I will use Group Policy to automatically map department network drives when users sign into the domain.

Examples:

- Accounting → A:
- HR → H:
- IT → I:

This will demonstrate centralized drive mapping and user-specific resource deployment using Active Directory Group Policy.
