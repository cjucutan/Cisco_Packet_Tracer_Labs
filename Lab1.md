# Lab 1 - Direct PC-to-PC Connection

## Objectives

- Connect two PCs directly without a switch
- Assign static IP addresses manually
- Test connectivity with ping
- Understand what a crossover cable does and why it is needed here

## Topology

- 2x PCs

## Steps

1. Add 2x PC-PT devices to the canvas.

2. From Connections, choose Copper Cross-Over cable. Connect PC0 FastEthernet0 to PC1 FastEthernet0.

![text](/Markdown%20_Images/Lab_1/Lab1pt1.png)

3. Click PC0 → Desktop → IP Configuration. Enter IP 192.168.1.10, Subnet 255.255.255.0.

![text](/Markdown%20_Images/Lab_1/Lab1pt2.png)

4. Repeat for PC1 with IP 192.168.1.20.

![text](/Markdown%20_Images/Lab_1/Lab1pt2.2.png)

5. Click PC0 → Desktop → Command Prompt. Run:
   ping 192.168.1.20

![text](/Markdown%20_Images/Lab_1/Lab1pt3.png)

## Breaking the Connection

- I wanted to explore what would happen if the two PCs were placed on different networks.

![text](/Markdown%20_Images/Lab_1/Lab1pt4.png)

- To test this, I opened the Command Prompt on PC0 and attempted to ping the new IP address assigned to PC1.

![text](/Markdown%20_Images/Lab_1/Lab1pt5.png)

- The ping failed, so I investigated why the devices could no longer communicate.

- The issue is related to the subnet mask.

- With a subnet mask of 255.255.255.0 (/24), devices must share the same network portion of the IP address to communicate directly.

- PC0 is on the 192.168.1.0/24 network, while PC1 is on a different network.

- Because the PCs are on separate networks and there is no router available to route traffic between them, the ping requests fail and the packets are dropped.

## What I learned

- Why a crossover cable is needed when connecting similar devices

- Manually configure static IP addresses
- How to use the ping command

- Devices must be in the same subnet to communicate directly without a router

- How a subnet mask determines whether devices are on the same network

- When devices are placed on different networks, a router is required to forward traffic between them

- How to troubleshoot basic connectivity issues by checking cable types, IP addresses, subnet masks, and ping results
