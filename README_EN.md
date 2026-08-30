# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/4dfc51a0-73f1-4e92-b63c-2db946ad162a)

## Results
-AD confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/0caefdd8-40b5-44b1-aa25-a676dad843d0)
![スクリーンショット](https://github.com/user-attachments/assets/98a31d9e-942d-45db-878a-d51c9325370e)

-OSPF confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/1f3d29cc-0e6e-49c9-aa92-9c850240d4ef)
![スクリーンショット](https://github.com/user-attachments/assets/c2e3c0b6-5a52-4586-8490-223ff98d4b34)

-ACL confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/de8c772c-c833-42b2-9fd6-de6a7ca373e6)
![スクリーンショット](https://github.com/user-attachments/assets/b4f40163-5aba-4298-8b59-a83b4476d351)

-NAT confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/5f25c276-c24d-4f0b-a2b4-5f17b7ff1f52)

-wireshark confirmation  
Arp  
317	4.058676	Private_66:68:02	Broadcast	ARP	68	Who has 192.168.30.1? Tell 192.168.30.10  
318	0.015342	c4:01:44:30:00:00	Private_66:68:02	ARP	64	192.168.30.1 is at c4:01:44:30:00:00

Icmp  
49	0.894836	192.168.30.10	192.168.20.1	ICMP	98	Echo (ping) request  id=0x52f1, seq=1/256, ttl=63 (reply in 50)  
50	0.016229	192.168.20.1	192.168.30.10	ICMP	98	Echo (ping) reply    id=0x52f1, seq=1/256, ttl=255 (request in 49)  
51	1.049250	192.168.30.10	192.168.20.1	ICMP	98	Echo (ping) request  id=0x53f1, seq=2/512, ttl=63 (reply in 52)  
52	0.015682	192.168.20.1	192.168.30.10	ICMP	98	Echo (ping) reply    id=0x53f1, seq=2/512, ttl=255 (request in 51)  
53	1.053028	192.168.30.10	192.168.20.1	ICMP	98	Echo (ping) request  id=0x54f1, seq=3/768, ttl=63 (reply in 54)  
54	0.014881	192.168.20.1	192.168.30.10	ICMP	98	Echo (ping) reply    id=0x54f1, seq=3/768, ttl=255 (request in 53)  
55	1.056545	192.168.30.10	192.168.20.1	ICMP	98	Echo (ping) request  id=0x55f1, seq=4/1024, ttl=63 (reply in 56)  
56	0.016173	192.168.20.1	192.168.30.10	ICMP	98	Echo (ping) reply    id=0x55f1, seq=4/1024, ttl=255 (request in 55)  
58	0.999816	192.168.30.10	192.168.20.1	ICMP	98	Echo (ping) request  id=0x56f1, seq=5/1280, ttl=63 (reply in 59)  
59	0.016342	192.168.20.1	192.168.30.10	ICMP	98	Echo (ping) reply    id=0x56f1, seq=5/1280, ttl=255 (request in 58)  

Ospf (Hello)  
![スクリーンショット](https://github.com/user-attachments/assets/d3762172-c755-4431-9d76-b090c5672d65)
![スクリーンショット](https://github.com/user-attachments/assets/3f8cbaf8-1aa6-4539-bcac-d031945df1a2)

Dhcp  

![スクリーンショット](https://github.com/user-attachments/assets/0676cc50-c37b-4635-9e5a-86140b6b348a)

## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as locala317	4.058676	Private_66:68:02	Broadcast	ARP	68	Who has 192.168.30.1? Tell 192.168.30.10
318	0.015342	c4:01:44:30:00:00	Private_66:68:02	ARP	64	192.168.30.1 is at c4:01:44:30:00:00
dmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
- Advertise outside destination to inside routers as default route when configuring NAT.
- Check if NIC of AD server is connected or not when we use LDAP port.

