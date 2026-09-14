

At a high level, TLS is implemented via the record protocol, which is in charge of transporting—and optionally encrypting—all lower-level messages exchanged over a connection. 

![[Pasted image 20251226164230.png]]

Each TLS record starts with a short header, which contains information about the record content type (or subprotocol), protocol version, and length. Message data follows immediately after the header
```
struct { 
	uint8 major; 
	uint8 minor; 
} ProtocolVersion; 

enum { 
	change_cipher_spec (20), 
	alert (21), 
	handshake (22), 
	application_data (23) 
} ContentType; 

struct { 
	ContentType type; 
	ProtocolVersion version; 
	uint16 length; /* Maximum length is 2^14 (16,384) bytes. */ 
	opaque fragment[TLSPlaintext.length]; 
} TLSPlaintext;
```

