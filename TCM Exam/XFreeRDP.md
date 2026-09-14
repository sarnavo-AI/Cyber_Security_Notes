# 10.0.0.225

![[Pasted image 20250716112408.png]]

![[Pasted image 20250716111133.png]]
WE GOT IN AS ADMINISTRATOR

# 10.0.0.25

![[Pasted image 20250716112433.png]]



![[Pasted image 20250716112215.png]]
We are a domain user, and a administrator here in this account

Now, we ran mimikatz here

![[Pasted image 20250716111608.png]]

But couldn't run the mimikatz in debug mode
![[Pasted image 20250716111734.png]]

Then after googling,  I found out that!,

in run.exe in windows after typing `secpol.msc`

![[Pasted image 20250716111951.png]]
That only administrators were allowed to have access, so from secretsdump, we got the username and password of local administrator

Now with local administrator
![[Pasted image 20250716112506.png]]

![[Pasted image 20250716112555.png]]

![[Pasted image 20250716112740.png]]

We were able to run!! mimikatz
![[Pasted image 20250716113007.png]]
but we didn't find anything juicy here

so we moved on to spray the password into other machines too


# 10.0.0.35
![[Pasted image 20250716115224.png]]

![[Pasted image 20250716115301.png]]

![[Pasted image 20250716115331.png]]
Nothing much interesting, let's see if mimikatz works here!

![[Pasted image 20250716120445.png]]

![[Pasted image 20250716120501.png]]
And we got it!!
