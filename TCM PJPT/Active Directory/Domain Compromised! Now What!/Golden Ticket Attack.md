![[Pasted image 20250711003700.png]]
`krbtgt` --> kerberos ticket granting ticket

Do a `lsadump` and get the `sid: which is S-1-5-21-190...` and the NTLM hashes 
![[Pasted image 20250711003756.png]]

then type out this command with `sid`, `NTLM`, `ppt (pass the ticket)` and the `rid` which is 500 for `Administrator` 
![[Pasted image 20250711003821.png]]

then type out `misc::cmd` and then another cmd will pop up with this and now you can go to any account using `dir` command 
![[Pasted image 20250711003835.png]]

