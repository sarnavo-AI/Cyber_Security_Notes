## What is AD?

We learned a lot of techniques, for external pen-testing, but suppose we are inside of a network, then how to escalate our privilege

![[Pasted image 20250620180207.png]]

--> It's an Identity Management Service (IMS)
--> Most Popular almost 99% companies use this
![[Pasted image 20250620180418.png]]

## Physical and Logical Components of AD
![[Pasted image 20250620180825.png]]

### Physical Components

Control everything, hosts the phone book
![[Pasted image 20250620181029.png]]

Ntds.dit file contains hashed password for many users
![[Pasted image 20250620181104.png]]


### Logical Components
![[Pasted image 20250620181813.png]]
![[Pasted image 20250620181832.png]]

![[Pasted image 20250620181852.png]]
![[Pasted image 20250620181907.png]]
![[Pasted image 20250620181923.png]]


![[Pasted image 20250620182001.png]]

## Lab Setup

Server Machine
	--> User: Administrator, Password: `P@$$w0rd!`
	--> Name of the PC: HYDRA-DC
	
	Now to make it Domain Controller
	Install AD

	--> Promoting the current node to Domain Controller
	--> Root Domain Name or (name of the forest): MARVEL.local
	--> DSRM (Directory Services Restore Mode) password: `P@$$w0rd!`
	--> NetBIOS Domain Name: MARVEL

	After Setup, you will login to MARVEL\Administrator, with above password
	Install Certificate Servives (to use LDAPS for verifying users in the domain)

	Now Create OUs, Users, Group Policies
		--> Now we just have a administrator and Guest account in users
		--> Copy of Administrator: (Domain Admin)
			--> Tony Stark : (User logon Name: tstark@MARVEL.local)
			--> Password12345! 
		--> Copy of Administrator: (Service Account)
			--> SQL Service: (User logon Name: SQLServie@MARVEL.local)
			--> MYpassword123#
			--> In the description, password is MYpassword123#
		
		--> New User:
			--> Frank Castle : (User logon Name: fcastle@MARVEL.local)
			--> Password1
		--> New User:
			--> Peter Parker: (User logon Name: pparker@MARVEL.local)
			--> Password2
	
	New File Share:
		--> SMB Share - Quick
		--> Name: hackme

	SetSPN for Service Account (for keberoasting attack)
		--> setspn -a HYDRA-DC/SQLService.MARVEL.local:60111 MARVEL\SQLServie

	Set Group Policy
		--> Disabling Windows Defender
		
		
	Setting Static IP:
		--> 192.168.138.136
		--> 255.255.255.0 (subnet)
		--> 192.168.138.2 (default gateway)
		--> Internet will be lost
	

User Machines
	Use Domain Join instead of online Microsoft Login

	User: frankcastle, Password1 (VM Name: Punisher-2)
		--> Name: THEPUNISHER
		--> 192.168.138.137
		--> DNS Should point to Domain Controller 

		--> Joining the account in "Access work or school"
		--> Join using Local Active Directory
		--> Domain Name: MARVEL.local
		--> Giving the userName: administrator, password: P@$$w0rd!
		--> then adding administrator to this local computer

		For Setting Up Local Administrators,
		--> Now Login as MARVEL\Administrator
			--> Using P@$$w0rd!

		--> Open "Local Users and Groups"
			--> Enabling administrator account (password should be identical)
				--> Password1!
			--> In groups, add fcastle@MARVEL.local as administrator






		
	User: peterparker, Password1 (VM Name: Spiderman-2)
		--> Name: SPIDERMAN
		--> 192.168.138.138
		--> DNS Should point to Domain Controller 
		
		--> Joining the account in "Access work or school"
		--> Join using Local Active Directory
		--> Domain Name: MARVEL.local
		--> Giving the userName: administrator, password: P@$$w0rd!
		--> then adding administrator to this local computer

		For Setting Up Local Administrators,
		--> Now Login as MARVEL\Administrator
			--> Using P@$$w0rd!
		
		--> Open "Local Users and Groups"
			--> Enabling administrator account (password should be identical)
				--> Password1!
			--> In groups
				--> Add pparker@MARVEL.local as administrator
				--> Add fcastle@MARVEL.local as administrator


		--> Logging in as .\peterparker
			--> Map Network Drive
				--> Z:\\HYDRA-DC\hackme
					--> Use different credentials:
							--> administrator
							--> P@$$w0rd!


![[Pasted image 20250701174939.png]]
![[Pasted image 20250701175621.png]]

