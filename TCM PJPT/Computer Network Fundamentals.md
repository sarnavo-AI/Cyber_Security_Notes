# IP Addresses

###### Layer 3 address in the OSI (which is used for routing)

Linux
	`ifconfig` 
Windows
	`ipconfig`

IP4 ---> 4 octets arranged, i.e, $2^{32}$ possible IP4, which is around ~ 4 Billion
		But we have a lot more devices and people than 4 Billion
		To Mitigate this problem we have introduced **NAT (Network Address Translation)** 
			![[Pasted image 20250214030238.png]]
		In Our House, mostly Class C is used, but big Orgs use Class A Private Networks

IP6 ---> Hexa-decimal format -->  $2 ^ {128}$ (More than number of atoms in our Earth)


# MAC Address

**MAC --> Media Access Control**
###### Used in Layer 2 (for switches to know which device it is)

**Format** --> `{00-ff}:{00-ff}:{00-ff}:{00-ff}:{00-ff}:{00-ff}`
			--> Uses hexa-decimal format
			--> The first 3 hexas combine up to make the identifiers, we can know the detail of our underlying hardware


# TCP and UDP

TCP --> Transmission Control Protocol
UDP --> User Datagram Protocol

Used in Layer 4, in sync with ports of a computer (~65000)

TCP --> Connected Oriented Protocol, uses 3-way Handshake [SYN -- SYN ACK -- ACK]
		Ex: HTTP, HTTPS, SSH, FTP, etc..
UDP --> Connectedless Protocol
		Ex: Video Streaming, DNS, Voiceover IP, etc...


# Common Port and Protocols

![[Pasted image 20250214032112.png]]

###### DNS uses both TCP and UDP

###### SMB is important, for file sharing (WannaCry used a SMB Exploit)
	Originally in 139, later windows implemented in 445 as well
###### TFTP --> Trivial FTP

# OSI Model

1. Physical Layer        -- Data Cables, cat6
2. Data Layer             -- Switching, MAC Address
3. Network Layer       -- IP Address
4. Transport Layer      -- TCP/UDP
5. Session Layer         -- Session Management
6. Presentation Layer -- WMV, JPEG, MOV
7. Application Layer   -- HTTP, SMTP

# Subnetting

CIDR Notation --> /24, /32 notation

basically tells us how many hosts are there.



