# Lab 001 — Packet Tracer Introduction

**Platform:** Cisco Packet Tracer  
**Course:** Jeremy's IT Lab — CCNA 200-301  
**Exercise:** Day 01 Lab — Packet Tracer Introduction  
**Reference:** [Jeremy's IT Lab video](https://www.youtube.com/watch?v=a1Im6GYaSno)  
**Status:** Topology screenshot reviewed; Packet Tracer project file included (not independently opened in Cisco Packet Tracer)

## Objective

Build a basic, multi-site network topology in Cisco Packet Tracer to become familiar with adding, naming, and connecting networking devices. Identify the roles of routers, Layer 2 switches, firewalls, and endpoints in a branch-to-branch network design.

## Network Topology

The screenshot shows two branch sites connected through a router representing the Internet, plus an external laptop labeled `Laptop0`. This laptop represents an outside endpoint in the training diagram; the screenshot does not demonstrate any attack.

- **New York:** PC1, PC2, SW1 (Cisco 2960), R1 (Cisco 2911), FW1 (Cisco ASA 5505)
- **Internet:** A Cisco 2911 router labeled `The Internet`, and Laptop0
- **Tokyo:** R2 (Cisco 2911), FW2 (Cisco ASA 5505), SW2 (Cisco 2960), SRV1, SRV2

![Completed Network Topology](Screenshots/network-topology.png)

### Logical Connections

```text
PC1 ─┐
     ├─ SW1 ─ R1 ─ FW1 ─ The Internet ─ R2 ─ FW2 ─ SW2 ─ SRV1
PC2 ─┘                         │                         └─ SRV2
                              │
                         Laptop0
```

**Design note:** The firewalls are placed differently at the two sites, matching the training exercise. Firewall placement depends on network architecture and security requirements.

## Implementation

The submitted screenshot confirms a Packet Tracer logical topology containing the devices and physical links listed above. The screenshot alone cannot establish whether devices were added manually or supplied by a starter file, which cable selection method was used, or whether the `.pkt` file has been saved. Record those workflow details only after confirming them.

## Verification

> The checkboxes below reflect what is visible in the submitted topology screenshot. The saved project file still needs to be verified.

- [x] All expected network devices appear in the logical workspace.
- [x] The New York branch is connected in the order PC1/PC2 → SW1 → R1 → FW1 → Internet.
- [x] The Tokyo branch is connected in the order Internet → R2 → FW2 → SW2 → SRV1/SRV2.
- [x] Laptop0 is connected to the Internet router.
- [x] Device labels are clear and connections match the reference diagram.
- [ ] The completed `.pkt` file opens successfully in Cisco Packet Tracer.
- [x] A screenshot of the finished topology is saved in `Screenshots/network-topology.png`.

**Link-state observation:** In the submitted screenshot, the endpoint-to-switch links show green indicators, while many router/firewall-facing links show red indicators. The image supports a completed topology layout, **not** an end-to-end working network. Router interfaces may require enabling/configuration in subsequent labs. No successful pings or traffic tests are claimed.

**Scope:** This introductory lab demonstrates topology construction only. IP addressing, routing, firewall security policies, and end-to-end connectivity have not been evidenced here.

## Key Concepts

| Component | Role in the topology |
| --- | --- |
| Router | Connects distinct networks and forwards IP packets between them when configured |
| Switch | Connects devices within a LAN and forwards Ethernet frames based on MAC addresses |
| Firewall | Can inspect and control permitted traffic according to configured security policies |
| PC / Server | Represents end-user systems and network services |
| Internet router | Simulates the intermediary network connecting the two sites |

## Lessons Learned

This exercise introduces the workflow of constructing network diagrams in a simulator, selecting different classes of devices, assigning meaningful device names, and connecting multi-site network components. It also illustrates that routers, switches, and firewalls serve distinct functions in network architecture.

## Next Steps

Proceed to the Day 02 connecting-devices lab and document cable selection, interface connections, and how cable/media types affect network design.

## Attribution

This project is a personal learning exercise based on [Jeremy's IT Lab](https://www.youtube.com/watch?v=a1Im6GYaSno). The documentation should reflect my own completed work and verification. Jeremy's course materials and original starter files belong to their respective owners.
