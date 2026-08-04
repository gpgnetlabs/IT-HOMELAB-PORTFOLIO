# Lab 007 - Active Directory User Management

## Overview

This lab focuses on common Active Directory administrative tasks performed by Help Desk Technicians and Junior Systems Administrators. The objective was to simulate real-world user lifecycle management within a Windows Server 2022 Active Directory environment.

---

## Lab Objectives

- Create domain user accounts
- Reset user passwords
- Force password changes
- Disable user accounts
- Move users between Organizational Units
- Assign Security Group membership
- Rename user accounts
- Review account properties
- Delete user accounts

---

## Environment

| Component | Value |
|----------|-------|
| Hypervisor | VMware Workstation |
| Server | Windows Server 2022 Standard Evaluation |
| Domain Controller | GPG-DC01 |
| Domain | gpg.local |
| Tool | Active Directory Users and Computers |

---

## Business Scenario

As the IT Administrator for **GPG Industries**, I was responsible for completing several common Active Directory administration requests submitted by Human Resources and the Help Desk.

The tasks included onboarding a new employee, resetting passwords, transferring users between departments, updating user information, assigning security permissions, and offboarding departing employees.

---

# Tasks Completed

## 1. Created a New Domain User

Created:

- James Wilson

Configured:

- Username
- Initial password
- Password change at next logon

---

## 2. Reset User Password

Reset the password for:

- Sarah Parker

Configured:

- Temporary password
- Forced password change at next logon

---

## 3. Disabled a User

Disabled:

- John Carter

Moved account to:

- Disabled Objects OU

---

## 4. Department Transfer

Moved:

- Emily Davis

From:

- HR

To:

- IT

---

## 5. Updated Security Group Membership

Added Emily Davis to:

- IT_Admins

Verified group membership.

---

## 6. Renamed User

Updated:

David Miller

to

David Anderson

Updated:

- Display Name
- Last Name
- User Logon Name

---

## 7. Reviewed Account Properties

Reviewed the Account tab for:

- Olivia Johnson

Verified account configuration.

---

## 8. Deleted Test User

Deleted:

- James Wilson

to simulate removal of an unused employee account.

---

# Skills Demonstrated

- Active Directory Administration
- Identity Management
- User Lifecycle Management
- Organizational Unit Administration
- Security Group Administration
- Windows Server Administration
- Enterprise Account Management

---

# Screenshots

| Screenshot | Description |
|------------|-------------|
| 01 | Create Domain User |
| 02 | Reset Password |
| 03 | Disabled User |
| 04 | User Transfer |
| 05 | Group Membership |
| 06 | User Rename |
| 07 | Account Properties |
| 08 | User Deletion |

---

# Technologies Used

- Windows Server 2022
- Active Directory Domain Services
- Active Directory Users and Computers
- VMware Workstation
- DNS
- Windows Authentication

---

# Lessons Learned

This lab reinforced the importance of properly managing the lifecycle of Active Directory user accounts. Instead of assigning permissions directly to users, access should be managed through Security Groups. Organizational Units provide logical organization while Security Groups simplify permission management and administration.

These tasks closely mirror daily responsibilities performed by Help Desk Technicians and Junior Systems Administrators in enterprise Windows environments.

---

# Skills for Employers

This project demonstrates experience with:

- Active Directory
- Windows Server 2022
- User Administration
- Identity and Access Management (IAM)
- Security Groups
- Organizational Units
- Help Desk Operations
- Enterprise User Management
