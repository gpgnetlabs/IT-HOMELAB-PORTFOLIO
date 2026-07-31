# Lab 003 - Windows NTFS Permissions & Access Control

## Objective

Configure and troubleshoot NTFS permissions using administrator and standard user accounts. This lab explores ownership, inheritance, security groups, effective permissions, and common access control scenarios found in Windows environments.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 11 Pro |
| Platform | Oracle VirtualBox |
| Administrator Account | gpgvm |
| Standard User | labuser |

---

## Skills Practiced

- NTFS Permissions
- File & Folder Ownership
- Security Groups
- Standard User vs Administrator
- Inheritance
- Explicit vs Inherited Permissions
- Allow vs Deny Permissions
- Effective Permissions
- Effective Access Tool
- Windows Security Troubleshooting

---

# Exercise 1 - Create a Test Environment

Created a dedicated folder for testing NTFS permissions.

Location:

```
C:\Shared\PermissionsLab
```

Created:

```
secret.txt
```

Purpose:

Provide a controlled environment for testing Windows access control.

---

# Exercise 2 - Inspect Existing Permissions

Reviewed the Security tab and Advanced Security Settings.

Verified:

- Folder owner
- Security principals
- Inherited permissions
- Permission entries

---

# Exercise 3 - Test Administrator Access

As the administrator account:

- Opened the folder
- Created files
- Edited files
- Renamed files
- Deleted files

Verified Full Control permissions.

---

# Exercise 4 - Test Standard User Access

Logged in as:

```
labuser
```

Initially observed that the standard user could:

- Open files
- Edit files
- Rename files
- Delete files

Investigation revealed this was caused by inherited **Modify** permissions granted to the **Authenticated Users** group.

---

# Exercise 5 - Configure NTFS Permissions

Configured folder permissions by:

- Disabling inheritance
- Converting inherited permissions to explicit permissions
- Removing unnecessary Modify permissions
- Retaining Full Control for:
  - SYSTEM
  - Administrators
- Granting Read & Execute permissions to the Users group

---

# Exercise 6 - Troubleshoot Access Issues

During testing, an explicit **Deny** permission was accidentally created.

Observed:

- Access Denied errors
- Administrator elevation prompts
- Permission conflicts

Resolved the issue by removing the explicit Deny entry and restoring the intended permissions.

---

# Exercise 7 - Verify Effective Access

Used the **Effective Access** tool to calculate the actual permissions assigned to `labuser`.

Verified Allowed:

- Read
- Read & Execute
- Traverse Folder
- Read Attributes

Verified Denied:

- Write
- Modify
- Delete
- Change Permissions
- Take Ownership
- Full Control

The calculated permissions matched the real-world testing performed during the lab.

---

# Troubleshooting

### Issue 1

**Problem**

Unable to access another user's profile folder.

**Cause**

Windows protects user profile folders (`C:\Users\<username>`) by default.

**Resolution**

Created a shared testing folder outside user profiles.

---

### Issue 2

**Problem**

Standard user could modify and delete files.

**Cause**

Inherited Modify permissions assigned to **Authenticated Users**.

**Resolution**

Reviewed inherited permissions and reconfigured access.

---

### Issue 3

**Problem**

Access was unexpectedly denied.

**Cause**

An explicit **Deny** permission overrode inherited Allow permissions.

**Resolution**

Removed the Deny entry and verified permissions using Effective Access.

---

# Key Concepts Learned

- NTFS Permissions
- Ownership
- Security Principals
- Group Membership
- Effective Permissions
- Permission Inheritance
- Explicit vs Inherited Permissions
- Allow vs Deny
- Effective Access
- Windows Security

---

# Skills Demonstrated

- Windows Administration
- Access Control Configuration
- Security Troubleshooting
- Permission Analysis
- Windows File System Security
- Technical Documentation

---

# Reflection

This lab demonstrated how Windows evaluates NTFS permissions using ownership, security groups, inherited permissions, and effective access.

I learned that effective permissions are determined by a combination of group memberships and NTFS permission entries rather than a single user account. I also observed how explicit Deny permissions override Allow permissions and how the Effective Access tool can be used to troubleshoot permission-related issues.

These concepts are essential for Help Desk, Desktop Support, Systems Administration, and Network Administration roles.

---

# Screenshots

| Screenshot | Description |
|------------|-------------|
| 01-folder-created.png | Created the PermissionsLab folder |
| 02-folder-properties.png | Verified folder properties |
| 03-owner-and-inheritance.png | Reviewed ownership and inherited permissions |
| 04-initial-security-permissions.png | Inspected initial NTFS permissions |
| 05-advanced-security-settings.png | Reviewed Advanced Security Settings |
| 06-user-profile-access-denied.png | Standard user blocked from another user's profile |
| 07-shared-folder-created.png | Created shared testing folder |
| 08-test-file-created.png | Created test file |
| 09-open-test-file.png | Opened the test file |
| 10-edit-test-file.png | Edited the test file |
| 11-administrator-group-removed.png | Removed administrator privileges from labuser |
| 12-authenticated-users-modify.png | Investigated inherited Modify permissions |
| 13-explicit-deny-created.png | Diagnosed an explicit Deny permission |
| 14-access-denied-rename.png | Verified permission restrictions during rename |
| 15-effective-access.png | Verified calculated permissions using Effective Access |

---

# Artifacts

- commands.txt
- notes.txt