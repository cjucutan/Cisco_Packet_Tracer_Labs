# Lab 2 - Building a LAN with a switch

## Objectives

- Build a star topology LAN
- Understand why a switch replaced the hub
- Observer MAC address learning
- Verify full mesh connectivity with ping

## Topology

- 4 PCs
- 1 switch

![text](/Markdown%20_Images/Lab_2/1.png)

## Steps

1. Add 1 switch and 4 PCs to the canvas

2. Connect each PC to the switch using Copper Straight-Through cables

![text](/Markdown%20_Images/Lab_2/2.png)

3. Assign static IPs to each PC from the table above

![text](/Markdown%20_Images/Lab_2/3.png)
![text](/Markdown%20_Images/Lab_2/4.png)
![text](/Markdown%20_Images/Lab_2/5.png)
![text](/Markdown%20_Images/Lab_2/6.png)

4. From PC0 Command Prompt, ping all other PCs

![text](/Markdown%20_Images/Lab_2/7.png)

5. Open Switch0 CLI and run: show mac address-table

![text](/Markdown%20_Images/Lab_2/8.png)

## What I learned

- Switches learned the MAC address by itself when PC0 sent pings to all other PCs. Every time a frame arrives on a port, the switch reads the source MAC address and records which port it came from
- A straight through cable was used when connecting PC to switch rather than a crossover cable because they don't use the same TX/RX pins to transmit and receive data.
- Hubs floods every fram out every port except the one it arrives one meaning every device sees every frame, thus having one big collision domain, eveyone sharesthe same bandwidth, and collisions slow everyone down
- A switch uses its MAC table to forward frames only to the correct port which means PCs can communicate simultaneously without colliding.
- Switches can have one collision domain per port, each device gets full bandwidth, and since there will be virtually no collisions, it can scale better
