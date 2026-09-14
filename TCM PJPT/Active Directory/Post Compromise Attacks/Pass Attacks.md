![[Pasted image 20250710162457.png]]

Using `crackmapexec`
![[Pasted image 20250710162519.png]]
We are interested in `pwn3d!`
In Hydra-DC too we got in the access, but we are not a local admin in that machine, so the pwn3d! is what we are interested in

We can also do it with hashes,
i) with metasploit
![[Pasted image 20250710162950.png]]
ii) with secretsdump
![[Pasted image 20250710163009.png]]


Now we can do pass the hashes attack
works only with NTLMv1 not NTLMv2
![[Pasted image 20250710163122.png]]

We can also Dump the hashes using `crackmapexec`
![[Pasted image 20250710163215.png]]

We can also enumerate all the shares
![[Pasted image 20250710163254.png]]

we can also get `lsa` which is `local security authority`
We can do it by secretdumps too but crackmapexec has the capability too.
![[Pasted image 20250710163418.png]]

There are many different builtin modules
![[Pasted image 20250710163522.png]]

like `lsassy`, it is responsible for enforcing security policy on the system, but it does store credentials too! that we might get from secretsdumps
![[Pasted image 20250710163545.png]]

We also have crackmapexec database of all the cracked machines
type in `cmedb`, then type help to get hold of all the commands!
![[Pasted image 20250710163705.png]]
