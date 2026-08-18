# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
## Window Server 2025 (Server)
- DNS Server: corp.example.com
## Windows 11 enterprise (Client)
## Things I noticed
- OU and Security Group are different things each other.  
  - OU: Object which GPO is applied to.  
  - Security Group: Object which authorization is applied to.
- Put ".\\" on the top when logging in as localadmin because it doesn't belong a domain.
- Copy running config to startup config when rebooting cisco router.
- Physical interface not assigned to any IP address when using dot1q.
