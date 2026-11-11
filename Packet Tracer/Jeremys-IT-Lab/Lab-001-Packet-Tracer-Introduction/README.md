# Lab 001 - Packet Tracer Introduction

**Course:** [Jeremy's IT Lab - Day 01](https://www.youtube.com/watch?v=a1Im6GYaSno)  
**Software:** Cisco Packet Tracer  
**Topic:** Getting familiar with network devices and a basic multi-site topology

## About this lab

I'm working through Jeremy's IT Lab as part of my CCNA studies and using this repository to keep track of the hands-on labs I complete.

This first lab is an introduction to Packet Tracer. The topology has two branches, one in New York and one in Tokyo, connected through a router representing the Internet. The goal here was to get familiar with the devices in the workspace and how they connect, rather than configure a working network.

## My topology

![Packet Tracer network topology](Screenshots/network-topology.png)

The network includes:

- **New York:** Two PCs (PC1 and PC2), a 2960 switch (SW1), a 2911 router (R1), and an ASA 5505 firewall (FW1).
- **Internet:** A 2911 router labeled `The Internet`, with a laptop connected to it.
- **Tokyo:** A 2911 router (R2), an ASA 5505 firewall (FW2), a 2960 switch (SW2), and two servers (SRV1 and SRV2).

The basic connection path looks like this:

```text
PC1 ─┐
     ├─ SW1 ─ R1 ─ FW1 ─ The Internet ─ R2 ─ FW2 ─ SW2 ─ SRV1
PC2 ─┘                         │                         └─ SRV2
                              │
                           Laptop0
```

## What I worked on

- Getting familiar with the Packet Tracer workspace and the different types of network devices.
- Looking at how PCs and servers connect to switches on each LAN.
- Following the connection from each branch through its router and firewall toward the Internet.
- Organizing the topology so the devices and links are easy to follow.

## What I noticed

The links between the end devices and their switches show green status indicators in my screenshot. Several of the links involving routers and firewalls show red indicators.

That's an important difference: **having devices connected in a diagram doesn't automatically mean the network is working.** There are still things like interface status, IP addressing, and routing to consider. I haven't included ping tests or claimed end-to-end connectivity for this introductory lab.

## What I'm taking away

This lab is a starting point for understanding the layout of a network. A switch connects devices on a local network, routers move packets between different IP networks, and firewalls can control which traffic is allowed through.

I'm keeping these notes as I go so I can look back at the basics when I move into configuring and troubleshooting networks in later labs.

## Lab files

- [Packet Tracer project](Lab-001.pkt)
- [Topology screenshot](Screenshots/network-topology.png)

## Credit

This lab is based on [Jeremy's IT Lab](https://www.youtube.com/watch?v=a1Im6GYaSno). The course and original exercise are his; these are my own study notes and lab evidence.
