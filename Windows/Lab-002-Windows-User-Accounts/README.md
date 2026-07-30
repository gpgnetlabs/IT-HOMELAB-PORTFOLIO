# Lab 002 – Windows Local User Accounts and Permissions

## Objective

The purpose of this lab was to explore how Windows manages local user accounts, user profiles, group memberships, administrative privileges, and User Account Control (UAC).

The primary goal was to compare the capabilities of a standard user account with those of an administrator account while learning how Windows protects the operating system through permission-based access control.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 11 Pro |
| Platform | Oracle VirtualBox |
| Virtual Machine | GPG-WIN11PRO-VM |
| Administrator Account | gpgvm |
| Standard User | labuser |

---

# Learning Objectives

By completing this lab I learned how to:

- View local Windows user accounts
- Create local user accounts
- Understand local user profiles
- Differentiate Standard Users from Administrators
- Inspect group memberships
- Understand User Account Control (UAC)
- Verify permissions using the command line
- Apply the Principle of Least Privilege
- Troubleshoot Windows permission issues

---

# Exercise 1 – Exploring Local Users

## Objective

Identify the built-in user accounts that Windows creates during installation.

## Steps Performed

- Opened Computer Management
- Navigated to:
```
Computer Management
└── Local Users and Groups
    └── Users
```

Observed the following accounts:

- Administrator
- DefaultAccount
- Guest
- gpgvm
- WDAGUtilityAccount

## What I Learned

Windows creates several built-in accounts automatically.

Some accounts exist only for Windows services and security features, while others are intended for system administration or recovery.

The built-in Administrator account is disabled by default for security reasons.

---

# Exercise 2 – Inspecting the Administrator Account

## Objective

Understand the difference between the built-in Administrator account and a normal administrator account.

## Steps Performed

Opened the properties of the Administrator account.

Examined:

- General
- Account Status
- Description

## What I Learned

The built-in Administrator account has unrestricted privileges.

Instead of using this account daily, Windows recommends using a normal account that belongs to the Administrators group.

This reduces security risks while still allowing administrative work.

---

# Exercise 3 – Inspecting the gpgvm Account

## Objective

Understand account properties.

## Steps Performed

Opened the properties for the gpgvm account.

Observed:

- Username
- Full Name
- Description
- Password Never Expires

## What I Learned

Windows separates a user's login name from their display name.

Additional account settings control password behavior and account management.

---

# Exercise 4 – Creating a Standard User

## Objective

Create a standard local user.

## Steps Performed

Created the account:

Username:
```
labuser
```

Configured:

- Full Name
- Description
- Password
- Password Never Expires

Verified the account appeared in Local Users and Groups.

## What I Learned

New users are automatically placed into the Users group unless additional permissions are assigned.

This follows Microsoft's Principle of Least Privilege.

---

# Exercise 5 – Logging Into labuser

## Objective

Observe what happens during a user's first login.

## Steps Performed

Signed out of gpgvm.

Logged into labuser.

Waited while Windows prepared the desktop.

## What I Learned

Windows automatically created a unique user profile.

The profile included:

- Desktop
- Documents
- Downloads
- AppData
- Registry profile
- User-specific settings

Each Windows account receives its own environment.

---

# Exercise 6 – Verifying Group Membership

## Objective

Confirm the permissions assigned to labuser.

## Steps Performed

Opened Command Prompt.

Executed:

```cmd
whoami /groups
```

Verified that Administrators did not appear.

## What I Learned

Although labuser could use Windows normally, it was only a member of the Users group.

Group membership determines many of the permissions available to a Windows account.

---

# Exercise 7 – Testing Standard User Permissions

## Objective

Determine what a standard user can and cannot do.

## Steps Performed

Opened Computer Management.

Navigated to Local Users and Groups.

Opened the New User dialog.

Attempted to create:

```
testuser
```

Received:

```
Access is denied.
```

## What I Learned

Windows allows some administrative interfaces to be viewed without granting permission to make changes.

Viewing information and modifying information are separate permissions.

---

# Exercise 8 – Testing User Account Control

## Objective

Understand how User Account Control protects Windows.

## Steps Performed

Attempted to run Command Prompt as Administrator.

Windows displayed a User Account Control prompt requesting administrator credentials.

## What I Learned

Standard users cannot approve elevated privileges themselves.

Windows requires administrator credentials before allowing administrative actions.

This process is known as credential elevation.

---

# Exercise 9 – Promoting labuser to Administrator

## Objective

Compare standard user permissions with administrator permissions.

## Steps Performed

Signed back into gpgvm.

Opened:

```
Computer Management
→ Local Users and Groups
→ Users
→ labuser
→ Member Of
```

Added:

```
Administrators
```

Signed out.

Logged back into labuser.

## What I Learned

Windows applies updated group memberships after a new login session.

The account remained the same user but received additional permissions through group membership.

---

# Exercise 10 – Verifying Administrator Permissions

## Objective

Compare the same account before and after elevation.

## Steps Performed

Repeated the previous permission tests.

Successfully created:

```
testuser
```

## What I Learned

The only thing that changed was the account's group membership.

Because labuser now belonged to the Administrators group, Windows allowed administrative actions that had previously been denied.

---

# Troubleshooting

## Issue

The New User dialog opened even though labuser was only a standard user.

Initially this appeared to contradict the expected behavior.

## Investigation

Instead of assuming the account had administrative privileges, I verified the account's permissions.

Executed:

```cmd
whoami /groups
```

Confirmed the account was not a member of Administrators.

Attempted to create a user.

Windows returned:

```
Access is denied.
```

## Resolution

The interface could be opened, but Windows blocked the actual administrative operation.

This demonstrated that read permissions and modify permissions are different.

---

# Key Concepts Learned

## Local User Accounts

Each user receives an individual identity within Windows.

---

## User Profiles

Each account receives its own:

- Desktop
- Downloads
- Documents
- Registry settings
- AppData

---

## Local Groups

Permissions are primarily assigned through groups rather than individual users.

Examples include:

- Users
- Administrators

---

## Principle of Least Privilege

Users should receive only the permissions necessary to perform their job.

---

## User Account Control (UAC)

Administrative actions require elevation.

Standard users provide administrator credentials.

Administrators approve elevation through UAC.

---

## Read vs Modify Permissions

Viewing a management interface does not guarantee permission to make changes.

---

# Skills Demonstrated

- Windows administration
- Local account management
- Group management
- User Account Control
- Windows security
- Permission troubleshooting
- Command-line verification
- Technical documentation

---

# Reflection

This lab significantly improved my understanding of how Windows manages permissions.

Before completing this exercise, I assumed that if a user could open an administrative tool, they likely had permission to use it. Through testing, I learned that Windows often allows users to view management interfaces while restricting the ability to make changes.

The most valuable lesson was observing how a single change in group membership completely changed what the account was permitted to do. Without changing the username or password, adding `labuser` to the Administrators group immediately enabled actions that were previously denied after signing into a new session.

This reinforced the importance of the Principle of Least Privilege and demonstrated how Windows uses groups, access control, and User Account Control together to protect the operating system.

This lab also reinforced the value of troubleshooting through observation and verification rather than assumptions. Instead of guessing why something behaved unexpectedly, I confirmed permissions using `whoami /groups`, repeated the tests after changing one variable, and compared the results. This methodical approach is an essential skill for IT support and system administration.

Overall, this lab provided practical experience with Windows account management and gave me a much stronger understanding of how authentication, authorization, and administrative privileges work in a Windows environment.

---

# Screenshots

- Local user accounts
- gpgvm account properties
- labuser account properties
- Member Of tab
- First login as labuser
- whoami /groups output
- Access Denied error
- UAC credential prompt
- Administrators group membership
- Successful creation of testuser

---

# Lab Cleanup

Completed the following cleanup tasks:

- Deleted the temporary `testuser` account.
- Returned `labuser` to the **Users** group (optional).
- Verified the lab environment was left in a clean state for future exercises.