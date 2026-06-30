# Lab 5 - VLANs - Network Segmentation

## Objectives

- Create two VLANs on a single switch

- Assign ports to VLANs

- Confirm that devices in different VLANs cannot communicate

- Understand why VLANs are used in real networks

## Topology

- 4 PCs

- 1 Managed Switch

![text](/Markdown%20_Images/Lab_5/1.png)

## Steps

- Enter these commands on switch0 on the CLI

![text](/Markdown%20_Images/Lab_5/2.png)

![text](/Markdown%20_Images/Lab_5/3.png)

![text](/Markdown%20_Images/Lab_5/4.png)

![text](/Markdown%20_Images/Lab_5/5.png)

## What I learned

- After configuring VLANs, I tried pinging from PC0 to PC2.
  - All 4 packets were lost when trying to ping
  - This means that although the PCs are physically connected to the same exact switch, the switch treats VLAN 10 and VLAN 20 as completely different networks
  - This also means that a frame from PC0 will only be forwarded to ports in VLAN 10 and vice versa

- If any malware were to attack lets say the sales VLAN, they cannot sniff traffic from IT or attempt to reach the IT servers
  - VLANs limit the blast radius of a security incident to only one segment

- Withouth VLANs, all devices on the switch share the same broadcast domain and a compromised device can see all traffic

- When I ran vlan brief is showed something interesting called VLAN 1
  - Upon further investigation, this is where all the ports belong to until it is explicitly moved
  - This would technically not be considered good practice to use VLAN 1 considering there are used for management traffic which would leave a massive confusion between user and management traffic

- Whenever I did the command 'switchport mode access', it configures the port to carry traffic for exactly one VLAN only, and the port is dedicated to end devices like PCs and printers
