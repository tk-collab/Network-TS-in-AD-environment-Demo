# Network-TS-in-AD-environment-Demo
## Virtualization Environment
- VirtualBox
- GNS3
![スクリーンショット](https://github.com/user-attachments/assets/055b24c8-8146-479d-980b-ce9fed9e9922)

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

## 気づいたこと/思い出したこと
- OUとセキュリティグループは別物  
    - OU: GPOを適用する単位  
    - セキュリティグループ: まとめて権限を付与するときの単位  
- localadminでログインする時はドメインに属さないから必ず.\付ける。
- Cisco routerは再起動する時はrunning configからstartup configにcopy必須
- dot1qを使う時は物理interfaceにはIPを持たせない
