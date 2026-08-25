# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3
![スクリーンショット](https://github.com/user-attachments/assets/7ce7cbe8-79c8-4bf3-ae76-b4f82cef6b10)

## 結果
-AD確認
![スクリーンショット](https://github.com/user-attachments/assets/6e7ae544-ac60-4b51-b26b-4180f86653f4)
![スクリーンショット](https://github.com/user-attachments/assets/0f92d431-b4a5-43d4-b46a-0c991bb0f846)

-OSPF確認  
![スクリーンショット](https://github.com/user-attachments/assets/256e5c3d-834c-4e6e-8a94-067ebd0525d4)
![スクリーンショット](https://github.com/user-attachments/assets/571b51ad-77cb-4ecf-9b33-bfaafba36d7d)

-ACL確認  

![スクリーンショット](https://github.com/user-attachments/assets/de8c772c-c833-42b2-9fd6-de6a7ca373e6)
![スクリーンショット](https://github.com/user-attachments/assets/b4f40163-5aba-4298-8b59-a83b4476d351)

-NAT確認  
![スクリーンショット](https://github.com/user-attachments/assets/64160931-798a-441d-8503-ead06a5a9cd5)

-wireshark確認  
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

## 気づいたこと/思い出したこと
- OUとセキュリティグループは別物  
    - OU: GPOを適用する単位  
    - セキュリティグループ: まとめて権限を付与するときの単位  
- localadminでログインする時はドメインに属さないから必ず.\付ける。
- Cisco routerは再起動する時はrunning configからstartup configにcopy必須
- dot1qを使う時は物理interfaceにはIPを持たせない
- NATを設定する時はデフォルトルートとして内部ルーターに広告する
