# Lab 005 - Ethernet LAN Switching (Days 05 and 06)

**Course:** [Jeremy's IT Lab - Ethernet LAN Switching](https://youtu.be/Ig0dSaOQDI8)  
**Software:** Cisco Packet Tracer  
**Topic:** MAC address learning, ARP, and Ethernet frame forwarding

## About this lab

This lab covers the Ethernet switching lessons from Days 05 and 06. I used a small network with two switches and four PCs to get a better idea of how switches learn MAC addresses and forward frames.

I also got to use the switch CLI to look at its MAC address table and clear the entries so I could see the difference.

## My topology

![Two switches and four PCs connected on the same LAN](lab-screenshot-02.png)

All four PCs are in the `192.168.1.0/24` network:

- PC1: `192.168.1.1`
- PC2: `192.168.1.2`
- PC3: `192.168.1.3`
- PC4: `192.168.1.4`

PC1 and PC2 connect to SW1, PC3 and PC4 connect to SW2, and the two switches are connected through their GigabitEthernet0/1 ports.

## What I worked on

I went into SW1's CLI and used `show mac address-table` to see which MAC addresses the switch had learned. The output showed **four dynamic entries in VLAN 1**:

- Two entries learned on `Gi0/1`, the link toward SW2.
- One entry on `Fa0/1`, toward PC1.
- One entry on `Fa0/2`, toward PC2.

Then I cleared the learned entries and checked the table again.

```text
SW1>enable
SW1#show mac address-table
SW1#clear mac address-table dynamic
SW1#show mac address-table
```

After clearing the dynamic entries, the second table display showed no MAC address entries at that moment.

![SW1 MAC address table before and after clearing dynamic entries](lab-screenshot-01.png)

## What I noticed

What stood out to me was that SW1 had learned four MAC addresses even though only two PCs were directly connected to it. The other two addresses were associated with `Gi0/1`, because those devices were reachable through SW2.

That helped make the MAC address table easier to understand. A switch doesn't need a separate cable to every device; it needs to know which **port leads toward** the destination MAC address.

Clearing the dynamic table also made the learning process more concrete. A switch can forget its learned entries, then learn them again as new frames arrive. The screenshot shows the table immediately after clearing, but doesn't show the relearning step.

## What I'm taking away

I'm getting a clearer picture of how Layer 2 forwarding works. A switch learns from the **source MAC address** of incoming frames. If it knows the destination MAC address, it can forward the frame to the correct port. If the destination is an unknown unicast address, it generally floods the frame within the VLAN.

I'm also keeping ARP and MAC learning separate in my head: ARP helps a host discover an IPv4 neighbor's MAC address, while the switch's MAC address table helps it decide where to send Ethernet frames.

This lab was about Ethernet switching and the MAC address table, not routing or configuring VLANs. My screenshots demonstrate the topology and the before-and-after MAC table commands; they don't independently show a ping or packet-by-packet ARP capture.

## Lab files

- [Packet Tracer project](Lab-005.pkt)
- [Network topology](lab-screenshot-02.png)
- [MAC address table and CLI commands](lab-screenshot-01.png)

## Credit

Based on Jeremy's IT Lab, Days 05 and 06, including the [Ethernet LAN Switching Packet Tracer lab](https://youtu.be/Ig0dSaOQDI8). These are my personal notes from working through the exercise.
