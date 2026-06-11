# Lab 2 – Building a LAN with a switch

## Overview

A four-PC star topology LAN built in Cisco Packet Tracer using a Cisco 2960 switch.

## Topology

- 4× PC-PT connected to a 2960 switch via straight-through cables
- Ports: Fa0/1 (PC0), Fa0/2 (PC1), Fa0/3 (PC2), Fa0/4 (PC3)

![text](./Markdown%20_Images/Lab2pt1.png)

## Key Concepts Demonstrated

- Star topology vs. bus/hub topology
- Switch MAC address learning (dynamic entries)
- Layer 2 unicast forwarding vs. flooding

## Verification

### Ping test (from PC0)

All 4 packets received with 0% loss across all three targets.

![text](./Markdown%20_Images//Lab2pt2.png)

### MAC address table (Switch0)

After the pings, the switch dynamically learned all 4 MAC addresses — one per port.

![text](./Markdown%20_Images//Lab2pt3.png)

## What I Learned

A switch builds a MAC address table dynamically by reading the source MAC of
every incoming frame. Once a destination MAC is known, traffic is forwarded
only to the correct port rather than flooded to all ports — this is the
fundamental efficiency gain over a hub.
