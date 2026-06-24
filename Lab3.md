# Lab 3 - DHCP Server Setup

## Objectives

- Configure a DHCP server to hand out IP addresses automatically
- Understand why servers need static IPs
- Observe the DORA handshake in Simulation Mode
- Verify leases with ipconfig

## Topology

- 1x Server
- 3 PCs
- 1 Switch

![text](/Markdown%20_Images/Lab_3/1.png)

![text](/Markdown%20_Images/Lab_3/2.png)

## Steps

1. Add Server-PT to previous lab 2 topology

![text](/Markdown%20_Images/Lab_3/3.png)

2. Click Server0 → Desktop → IP Configuration. Set static IP 192.168.1.1, mask 255.255.255.0.

![text](/Markdown%20_Images/Lab_3/4.png)

3. Click Server0 → Services → DHCP. Turn service On. Enter pool settings above. Click Add.

![text](/Markdown%20_Images/Lab_3/5.png)

4. On each PC: Desktop → IP Configuration → select DHCP radio button.

5. Wait a few seconds. Each PC should populate its IP automatically.

![text](/Markdown%20_Images/Lab_3/6.png)

6. On each PC run: ipconfig and confirm they each got a unique IP.

![text](/Markdown%20_Images/Lab_3/7.png)

## What I learned

- If a server used DHCP, its IP would change, and devices would fail to connect, therefore the server must have an IP that would never change and that is a static IP
- A server uses a static IP because other devices must always know where to find it
- Discover (DORA) = A PC broadcasts a message asking if there is any DHCP server out there
- Offer (DORA) = The server is replying with an offer which in this case is an IP
- Request (DORA) = PC responds to server by requesting for that IP address
- Acknowledge (DORA) = Server says yes to the request and the PC can now use the IP address
- Since I set the max users to 50 thats means if there is a 51st device that sends a discover message, the server would have no available addresses to offer, and the pool then becomes exhausted.
- When a DHCP lease expires, devices usually try to renew early so they can keep the same IP
- Network IPs get recycled when the DHCP lease expires
