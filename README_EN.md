# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/31452df4-243c-4d62-bcc7-9387751e6458)

## Results
-AD confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/0caefdd8-40b5-44b1-aa25-a676dad843d0)
![スクリーンショット](https://github.com/user-attachments/assets/98a31d9e-942d-45db-878a-d51c9325370e)
![スクリーンショット](https://github.com/user-attachments/assets/08e65991-9e57-4fd6-9a0f-f73f25df5cf5)
![スクリーンショット](https://github.com/user-attachments/assets/8066b283-088f-4a64-a4bc-2a7d9e0fffa9)
![スクリーンショット](https://github.com/user-attachments/assets/418458e1-eef3-46d7-b1a7-54d977a1dcfa)
![スクリーンショット](https://github.com/user-attachments/assets/613c20bb-e1cf-4ac2-a220-e8c1f39695d4)
![スクリーンショット](https://github.com/user-attachments/assets/d0e35c79-2ef1-457a-b38b-748a2736403e)


-OSPF confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/1f3d29cc-0e6e-49c9-aa92-9c850240d4ef)
![スクリーンショット](https://github.com/user-attachments/assets/c2e3c0b6-5a52-4586-8490-223ff98d4b34)

-ACL confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/de8c772c-c833-42b2-9fd6-de6a7ca373e6)  
```text
R1#show access-lists
Extended IP access list BLOCK_PC1_TO_PC2
    10 deny ip host 192.168.10.10 host 192.168.20.10 (15 matches)
    20 permit ip any any
```
The number of matches increases.
```text
R1#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
R1(config)#ip access-list extended BLOCK_PC1_TO_PC2
R1(config-ext-nacl)#no 10
```
```text
PC1> ping 192.168.20.10
84 bytes from 192.168.20.10 icmp_seq=1 ttl=62 time=32.765 ms
84 bytes from 192.168.20.10 icmp_seq=2 ttl=62 time=37.648 ms
84 bytes from 192.168.20.10 icmp_seq=3 ttl=62 time=37.899 ms
84 bytes from 192.168.20.10 icmp_seq=4 ttl=62 time=36.728 ms
84 bytes from 192.168.20.10 icmp_seq=5 ttl=62 time=37.708 ms
```
Once we delete the ACL ping become successful.

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

-Syslog  
/etc/rsyslog.d/10-remote.conf
```text
module(load="imudp")  #Receive as UDP
input(type="imudp" port="514")  #Await as UDP via 514 port

if ($fromhost-ip != "127.0.0.1") then {
    action(type="omfile" file="/var/log/remote-syslog.log")
    stop
}
```

## Things I noticed and remembered.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
- Advertise outside destination to inside routers as default route when configuring NAT.
- Check if NIC of AD server is connected or not when we use LDAP port.
- Check another TTY even if it looks frozen in case of Linux OS.
- The Well known port of Syslog is 514.
- Linux command "tail" show logs of the path identified.
- "apt" is used on Ubuntu or Debian to install, update or remove packages.
- Edit Netplan when adding a network adapter in Ubuntu.
- Update Ubuntu package repository with apt command before installing packages.
- DSRM stands for Directry Service Recovery Mode. Therefore, it doesn't mean domain account.
- The port number of LDAP is "389".
