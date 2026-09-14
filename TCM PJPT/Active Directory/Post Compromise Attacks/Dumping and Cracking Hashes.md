sGet info using secretsdump
![[Pasted image 20250710165756.png]]

there is tool called as `wdigest` installed by default in older windows machine like 7, etc... where can get clear text passwords!! nowadays it's turned off in newer machines but can turn it back on

We can also pass by hashes
![[Pasted image 20250710170146.png]]

Methodology:
Late.pyral to lateral till you vertically escalate
![[Pasted image 20250710170226.png]]

Now to crack the hashes you just need the NT portion, not the LM portion
![[Pasted image 20250710170331.png]]

We will use module 1000
![[Pasted image 20250710170351.png]]![[Pasted image 20250710170426.png]]
