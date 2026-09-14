Picked up by practically any anti virus software, so not recommended
![[Pasted image 20250710235637.png]]

We take it into peterparker machine, where the file sharing is enabled by default administrator credentials signing

![[Pasted image 20250711000418.png]]

We will change the privilege to debug to use the entire set of functionality to use

![[Pasted image 20250711000500.png]]

then we will run `sekurlsa`
![[Pasted image 20250711000550.png]]

If we check the `logonPasswords` then we will see interesting things
![[Pasted image 20250711000641.png]]
We get the not hashed `MARVEL\Administrator` password right away!!
Due to the file share enabled by default admin creds sign-ins


