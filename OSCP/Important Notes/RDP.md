To Create a virtual Network share while RDP
`rdesktop -r disk:linuxshare=/home/kali/Downloads -u offsec -p lab 192.168.241.61

`xfreerdp /v:192.168.204.227 /u:nadine /p:'123abc' /drive:linuxshare,/home/kali/Downloads /cert:ignore

`xfreerdp /v:192.168.204.227 /u:.\nadine /p:'123abc' /drive:linuxshare,/home/kali/Downloads /cert:ignore`

`xfreerdp /v:192.168.204.227 /u:marketingwk02\\nadine /p:'123abc' /drive:linuxshare,/home/kali/Downloads /cert:ignore`

The distinction matters:

| Username               | Meaning                            |
| ---------------------- | ---------------------------------- |
| `nadine`               | Ambiguous; Windows decides context |
| `.\nadine`             | Local user on the target machine   |
| `marketingwk02\nadine` | Local user on `marketingwk02`      |
| `DOMAIN\nadine`        | Domain account                     |
