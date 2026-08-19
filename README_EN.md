# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/9ff90365-6cb5-4849-836a-6404132f1a12)

## Results  
![スクリーンショット](https://github.com/user-attachments/assets/0caefdd8-40b5-44b1-aa25-a676dad843d0)

![スクリーンショット](https://github.com/user-attachments/assets/98a31d9e-942d-45db-878a-d51c9325370e)

## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
