# Lab 004 -- Active Directory Domain Controller Installation

## Objective

Deploy a Windows Server 2022 Domain Controller by installing Active
Directory Domain Services (AD DS), configuring DNS, promoting the server
to a Domain Controller, and creating a new Active Directory forest.

## Environment

-   VMware Workstation
-   Windows Server 2022 Standard Evaluation
-   Server Name: GPG-DC01
-   Static IP: 192.168.177.10
-   Domain: gpg.local

## Skills Demonstrated

-   Configured static IPv4 addressing
-   Renamed Windows Server
-   Installed AD DS role
-   Installed DNS Server
-   Promoted server to Domain Controller
-   Created a new Active Directory forest
-   Configured DSRM password
-   Verified Active Directory installation
-   Logged in with domain Administrator account

## Configuration

Hostname: GPG-DC01

IP Address: 192.168.177.10

Subnet Mask: 255.255.255.0

Default Gateway: 192.168.177.2

Preferred DNS: 192.168.177.10

Alternate DNS: 192.168.177.2

Forest: gpg.local

NetBIOS: GPG

## Lab Tasks Completed

-   Installed Windows Server 2022
-   Renamed the server
-   Assigned a static IP address
-   Configured DNS settings
-   Added the AD DS role
-   Promoted the server to a Domain Controller
-   Created the gpg.local forest
-   Rebooted into Directory Services
-   Verified Active Directory tools were installed

## Screenshots

1.  Server Manager Dashboard
2.  Local Server Properties
3.  Static IP Configuration
4.  AD DS Installation Wizard
5.  Promote Server to Domain Controller
6.  New Forest (gpg.local)
7.  Prerequisite Check
8.  Successful Installation
9.  Active Directory Users and Computers
10. DNS Manager

## Commands Used

GUI: - Server Manager - Active Directory Users and Computers - DNS
Manager

PowerShell: Get-ADDomain Get-ADForest ipconfig /all hostname

## Technologies

-   Windows Server 2022
-   Active Directory Domain Services
-   DNS
-   VMware Workstation
-   TCP/IP
-   IPv4
-   Microsoft Management Console

## What I Learned

-   Why Domain Controllers are the heart of an Active Directory
    environment.
-   Importance of static IP addressing before AD installation.
-   Relationship between AD DS and DNS.
-   How a new forest is created.
-   How enterprise authentication begins with a Domain Controller.
