# Lab 004 – Windows Print Spooler Troubleshooting

## Objective

Investigate and resolve a Windows printing issue by identifying, diagnosing, and restoring the Print Spooler service.

---

## Skills Demonstrated

- Windows Services
- Print Spooler Troubleshooting
- Windows Administration
- Service Management
- Troubleshooting Methodology
- Root Cause Analysis

---

## Environment

| Component | Value |
|----------|-------|
| Hypervisor | VMware Workstation |
| Operating System | Windows 11 Pro |
| User | labuser |
| Service | Print Spooler |

---

## Business Scenario

A user reports they cannot print documents to the office printer.

As the Help Desk Technician, your task is to identify the cause of the issue, restore printing functionality, and verify the resolution.

---

## Troubleshooting Process

### Step 1

Interview the user.

Questions asked:

- Are you the only person affected?
- Do print jobs appear in the queue?
- Are there any error messages?
- Has printing worked before?

---

### Step 2

Develop a hypothesis.

Possible causes:

- Print Spooler service stopped
- Printer offline
- Incorrect default printer
- Network connectivity issue
- Driver issue
- Permission issue

---

### Step 3

Verify Print Spooler.

Open:

Services

Locate:

Print Spooler

Status:

Running

Startup Type:

Automatic

---

### Step 4

Simulate Failure

Stop the Print Spooler service.

Observe:

- Printing fails.
- Print queue unavailable.

---

### Step 5

Resolve

Restart Print Spooler.

Confirm:

- Service running.
- Printing restored.

---

## Commands Used

```powershell
Get-Service Spooler

Start-Service Spooler

Stop-Service Spooler

Restart-Service Spooler
```

---

## Verification

- Print Spooler running
- Startup Type Automatic
- Test print successful

---

## Lessons Learned

- Printing depends on the Print Spooler service.
- Always verify Windows services before reinstalling drivers.
- Form hypotheses before changing configurations.
- Verify the fix after implementing it.

---

## Technologies

- Windows 11 Pro
- Windows Services
- PowerShell
- VMware Workstation
- Print Management

---

## Screenshots

1. Services Console
2. Print Spooler Running
3. Print Spooler Stopped
4. PowerShell Commands
5. Print Spooler Restarted
6. Successful Test Print

---

## Skills for Employers

This lab demonstrates practical experience with:

- Windows troubleshooting
- Service management
- Help Desk workflows
- Root cause analysis
- PowerShell fundamentals