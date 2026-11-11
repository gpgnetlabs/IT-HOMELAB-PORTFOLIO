# Lab 001 — Packet Tracer Introduction

| Field | Details |
| --- | --- |
| Platform | Cisco Packet Tracer |
| Course | Jeremy's IT Lab — CCNA 200-301 |
| Exercise | Day 01 Lab — Packet Tracer Introduction |
| Focus | Identify and connect common network devices |
| Verification | Topology reviewed visually; end-to-end communication not tested |
| Reference | [Jeremy's IT Lab — Day 01](https://www.youtube.com/watch?v=a1Im6GYaSno) |

## Objective

Explore Cisco Packet Tracer by examining a simulated multi-site enterprise network. Recognize common infrastructure components and understand their position in the topology, including end devices, switches, routers, firewalls, and an Internet-facing connection.

## Network Topology

The exercise contains two branch locations—New York and Tokyo—connected through a router labeled **The Internet**. An external laptop is also attached to the central router.

```text
New York Branch                                                Tokyo Branch
PC1 ─┐                                                            ┌─ SRV1
     ├─ SW1 ─ R1 ─ FW1 ─ The Internet ─ R2 ─ FW2 ─ SW2 ──────────┤
PC2 ─┘                       │                                    └─ SRV2
                            │
                         Laptop0
```

### Device Inventory

| Location | Devices | Role |
| --- | --- | --- |
| New York | PC1, PC2 | User endpoints |
| New York | SW1 (Cisco 2960-24TT) | LAN access switch |
| New York | R1 (Cisco 2911) | Branch router |
| New York | FW1 (ASA 5505) | Firewall |
| Transit | The Internet (Cisco 2911) | Router representing WAN/Internet connectivity |
| Transit | Laptop0 | External endpoint |
| Tokyo | R2 (Cisco 2911) | Branch router |
| Tokyo | FW2 (ASA 5505) | Firewall |
| Tokyo | SW2 (Cisco 2960-24TT) | LAN access switch |
| Tokyo | SRV1, SRV2 | Server endpoints |

## Implementation Summary

1. Opened the introductory Packet Tracer exercise and reviewed the logical workspace.
2. Identified and labeled the endpoints, access switches, routers, and firewalls at both sites.
3. Reviewed how the New York and Tokyo network segments are linked through the central Internet router.
4. Captured the completed logical topology for review.

The screenshot establishes the final layout, but not whether devices were placed from scratch, provided in a starter file, or configured through the CLI. Those steps are deliberately not claimed.

## Verification and Observations

| Check | Result | Evidence |
| --- | --- | --- |
| New York endpoints connect to SW1 | Observed | PC1 and PC2 linked to SW1 |
| Tokyo servers connect to SW2 | Observed | SRV1 and SRV2 linked to SW2 |
| Both branches reach the central router via their routers/firewalls | Topology present | Cabled path visible |
| External laptop is linked to the central router | Observed | Laptop0 connection visible |
| All inter-device links operational | Not established | Several router/firewall-facing links show red status |
| End-to-end IP connectivity | Not tested | No ping results or IP addressing provided |
| Saved Packet Tracer project opens successfully | Pending | `.pkt` file not yet supplied |

**Link-state note:** Green indicators are visible on the PC/server-to-switch connections. Multiple router/firewall-facing connections display red indicators. This is a topology familiarization exercise, not proof of a fully configured production network.

## Key Networking Concepts

- **Access switch:** Connects LAN devices and forwards Ethernet frames using MAC addresses.
- **Router:** Connects different IP networks and forwards packets when interfaces and routes are configured.
- **Firewall:** Enforces security policy by permitting or denying traffic based on its configuration.
- **End device:** A workstation or server that sends or receives network traffic.
- **WAN/Internet representation:** Models connectivity between separate geographic locations.

## Lessons Learned

- A logical network diagram makes it easier to identify the role of each device and trace the expected communication path.
- Different devices serve distinct purposes: switches primarily provide LAN connectivity, while routers interconnect networks and firewalls enforce security controls.
- A connected cable on a diagram does not guarantee that the interface is operational or that devices can exchange IP packets.
- Validating a network requires additional checks, such as interface state, IP settings, routing, and connectivity tests.

## Evidence and Project Files

- **Topology screenshot:** Reviewed from the completed exercise; upload planned to `Screenshots/network-topology.png`.
- **Packet Tracer file:** To be added as `Lab-001.pkt` when available.

Once the screenshot is uploaded, add `![Network topology](Screenshots/network-topology.png)` here.

## Next Steps

Continue to the next Packet Tracer exercise and document cabling choices, active interfaces, configuration commands, and validation results as they become part of the coursework.

## Attribution

Personal lab notes based on [Jeremy's IT Lab](https://www.youtube.com/watch?v=a1Im6GYaSno). The original video and course materials remain the property of their creator. These notes record observed results from the user's Packet Tracer exercise.
