# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3
<img width="816" height="493" alt="Network-TS-In-AD environment" src="https://github.com/user-attachments/assets/3546836b-6809-4253-bd31-a5e76dfccc2b" />

## Window Server 2025 (Server)
- DNS Server: corp.example.com
## Windows 11 enterprise (Client)
## Things I noticed and I reminded.
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
