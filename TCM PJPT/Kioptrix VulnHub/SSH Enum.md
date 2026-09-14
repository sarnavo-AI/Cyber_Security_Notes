We try this at last because we are doing a exploit here for the passwords, rather doing enum
So why?? to get the banner, like who created or what version

Usage:
	--> ssh "IP"
	--> ssh "IP" -oKexAlgorithms=+diffie-hellman-group1-sha1
	--> ssh "IP" -oKexAlgorithms=+diffie-hellman-group1-sha1 -c aes128-cbc

	for the Algorithm used for key exchange and the cipher used!


	