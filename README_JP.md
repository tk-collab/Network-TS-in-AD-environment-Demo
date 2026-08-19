# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3
<img width="816" height="493" alt="Network-TS-In-AD environment" src="https://github.com/user-attachments/assets/b4d69749-de35-4035-b3e9-e3573893eefd" />

## Window Server 2025 (Server)
- DNS Server: corp.example.com
## Windows 11 enterprise (Client)
## 気づいたこと/思い出したこと
- OUとセキュリティグループは別物  
    - OU: GPOを適用する単位  
    - セキュリティグループ: まとめて権限を付与するときの単位  
- localadminでログインする時はドメインに属さないから必ず.\付ける。
- Cisco routerは再起動する時はrunning configからstartup configにcopy必須
- dot1qを使う時は物理interfaceにはIPを持たせない
