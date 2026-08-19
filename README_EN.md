# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3  
![スクリーンショット](https://github.com/user-attachments/assets/9ff90365-6cb5-4849-836a-6404132f1a12)

## Results  
## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
