# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3
<img width="816" height="493" alt="Network-TS-In-AD environment" src="https://github.com/user-attachments/assets/99d92e80-6270-49f8-99e8-72399b42bca7" />

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
