SMB --> file sharing protocol for windows machine used for printers and scanners

msfconsole --> most popular interface to use MetaSpoilt FrameWork (MSF)
	--> Exploits
	--> Auxiliary (for scanning and enum and many other things)
	--> Post
	--> Payload
	--> Encoders
	--> nops
	--> evasion

for this we are gonna look into Auxiliary.
--> Usage: search smb
then set RHOSTS (remote Host) (the target machine)

then we will use "smbclient" in cli
Usage: smbclient -L "IP"
	--> -L (list all)
