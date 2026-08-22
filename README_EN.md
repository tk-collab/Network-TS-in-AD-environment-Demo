# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/b369d2a7-cc46-4d08-ae6e-1a4ad7d39734)

## Results
-AD confirmation  
![スクリーンショット](https://github.com/user-attachments/assets/0caefdd8-40b5-44b1-aa25-a676dad843d0)

![スクリーンショット](https://github.com/user-attachments/assets/98a31d9e-942d-45db-878a-d51c9325370e)

-OSPF confirmation  

![スクリーンショット](https://github.com/user-attachments/assets/1f3d29cc-0e6e-49c9-aa92-9c850240d4ef)

![スクリーンショット](https://github.com/user-attachments/assets/c2e3c0b6-5a52-4586-8490-223ff98d4b34)

## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
