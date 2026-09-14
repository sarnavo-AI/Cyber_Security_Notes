We all have IPv6, but we don't use it, so does the DNS for this, the answer is No One!!
So we as the hacker machine spoof for DNS and the relay it back to domain controller

This event can occur even doing small things like Restarting or logging in 

	ALWAYS RUN THIS ATTACK IN SHORT SPRINTS LIKE 5-10MINS, it might compromise the network itself

So we will be using `mitm6` and `ntlmrelayx`

First setup the `ntlmrelayx`-6
![[Pasted image 20250709191230.png]]
-6 --> IPv6
-t --> domain IP
-wh --> some fake wpad
-l --> for loot, create a folder for the dumps using `ldpsdomaindumps`

then run 
![[Pasted image 20250709191424.png]]

Now restart the punisher machine
![[Pasted image 20250709191654.png]]
Already a success, just by rebooting

Check the lootme folder for dumps
![[Pasted image 20250709191745.png]]

Logging in as administrator in punisher machine
![[Pasted image 20250709191907.png]]

![[Pasted image 20250709192017.png]]
Created a new user in Domain Controller LOL

![[Pasted image 20250709192105.png]]
This is user going to have access to enterprise admin group and which inturn will help us run the `secretsdump.py`

![[Pasted image 20250709192730.png]]
