
nmap -T4 -p- -A ''IP''

-T4 --> 4 thread (most optimal)
-p- --> all possible ports
-A --> all types of enumerations

-sS --> sneak scan for TCP (SYN SYNACK ACK  to SYN SYNACK RST)
-sU --> for UDP

