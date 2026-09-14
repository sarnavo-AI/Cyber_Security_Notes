![[Pasted image 20250710171032.png]]
Our DC is our KDC --> key distribution center

We request we TGT, which is ticket, to access our application Server, which is our SQL service account, since we already know that `fcastle` is an account from `pass attack`, so we login and get the TGS, which contains the hashes of the service account. then attempt to crack it.

![[Pasted image 20250710171656.png]]
![[Pasted image 20250710171710.png]]


