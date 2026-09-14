![[Pasted image 20250710173105.png]]
Delegate is when you log in as user or log in via remote desktop

First let us login as fcastle, 
then using `psexec` we get a shell in the machine,
then we load `incognito`
then `list_tokens -u`
![[Pasted image 20250710173423.png]]

then we we impersonate the token
![[Pasted image 20250710173601.png]]
we log into that

But now we cannot do anything because this user is not domain admin, so what if we log in into punisher machine using `MARVEL\Administrator` account, then we get admin tokens too
![[Pasted image 20250710173755.png]]

![[Pasted image 20250710173812.png]]

Now, since we have this and we logged in as domain administrator account we add accounts,
![[Pasted image 20250710173927.png]]
Now hawkeye, becomes a domain admin, so now we run secretsdump against this,

![[Pasted image 20250710174015.png]]

