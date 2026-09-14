
The handshake is the most elaborate part of the TLS protocol, during which the sides negotiate connection parameters and perform authentication. 

This phase usually requires **6 to 10 messages**, depending on which features are used.

In practice, we see three common flows: 
	(1) Full handshake with server authentication
	(2) abbreviated handshake that resumes an earlier session
	(3) handshake with client and server authentication.

Handshake protocol messages start with a header that carries the message type (1 byte) and length (3 bytes). The remainder of the message depends on the message type: 

```
struct { 
	HandshakeType msg_type; 
	uint24 length; 
	HandshakeMessage message; 
} Handshake;
```


# Full Handshake

Every TLS connection begins with a handshake. If the client hasn’t previously established a session with the server, the two sides will **execute a full handshake in order to negotiate a TLS session**. 

During this handshake, the client and the server will perform four main activities: 
1. Exchange capabilities and agree on desired connection parameters. 
2. Validate the presented certificate(s) or authenticate using other means. 
3. Agree on a shared master secret that will be used to protect the session. 
4. Verify that the handshake messages haven’t been modified by a third party.