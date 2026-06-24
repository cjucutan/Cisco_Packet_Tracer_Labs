# Lab 4 DNS and Basic Services

## Objectives

- Configure a DNS server to resolve hostnames to IP addresses
- Set up a basic HTTP web server
- Use nslookup to test DNS resolution
- Access a webpage by hostname instead of IP

## Topology

- 1 Server
- 3 PCs
- 1 Switch

![text](/Markdown%20_Images/Lab_4/1.png)

## Steps

1. Use your Lab 3 topology. Keep DHCP running on Server0.

2. Click Server0 → Services → DNS. Turn DNS service On.

![text](/Markdown%20_Images/Lab_4/2.png)

3. Add an A record: Name = server.local, Address = 192.168.1.1. Click Add.

![text](/Markdown%20_Images/Lab_4/3.png)

4. Add a second A record: Name = www.local, Address = 192.168.1.1. Click Add.

![text](/Markdown%20_Images/Lab_4/4.png)

5. Click Server0 → Services → HTTP. Confirm it is On. Edit the default HTML page if you want.

![text](/Markdown%20_Images/Lab_4/5.png)

6. On each PC: Desktop → IP Configuration → DNS Server field. Enter 192.168.1.1.

![text](/Markdown%20_Images/Lab_4/6.png)

7. On PC0 → Desktop → Command Prompt, run:
   nslookup server.local
   nslookup www.local

![text](/Markdown%20_Images/Lab_4/7.png)

8. On PC0 → Desktop → Web Browser. Type http://www.local and press Go.

![text](/Markdown%20_Images/Lab_4/8.png)

## What I learned

- Without DNS, PC0 cannot use names to access the web server
- PC0 would have to use the server's IP address to access the web server
- Using IPs directly is hard because it's hard to remember
- If the IP of the web server changes, everything breaks
- DNS fixes these problems above by letting users rely on easy names while the IPs can change
- An A record maps a domain name to an IPv4 address
- nslookup sends the query to the configured DNS server
