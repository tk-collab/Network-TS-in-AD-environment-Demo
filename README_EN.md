# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/9ff90365-6cb5-4849-836a-6404132f1a12)

## Results  
![スクリーンショット](https://github.com/user-attachments/assets/6e7ae544-ac60-4b51-b26b-4180f86653f4)
![スクリーンショット](https://github.com/user-attachments/assets/0f92d431-b4a5-43d4-b46a-0c991bb0f846)

## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
