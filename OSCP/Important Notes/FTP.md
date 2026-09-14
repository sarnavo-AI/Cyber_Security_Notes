https://www.jscape.com/blog/active-v-s-passive-ftp-simplified

Active vs Passive

We need binary encoding because **FTP defaults to ASCII text mode**, which corrupts non-text files like `.exe`, `.zip`, and images during transfer.

Here is exactly why changing to binary mode is necessary:

1. The Line Ending Problem (ASCII Mode)

Different operating systems use different characters to mark the end of a line in a text file:

- **Linux/Unix:** Uses Line Feed (`LF` or `\n`)
- **Windows:** Uses Carriage Return + Line Feed (`CRLF` or `\r\n`)

When FTP is in ASCII mode, it tries to be "smart." If you send a file from Kali Linux to a Windows server, the FTP client automatically scans the file and replaces every `LF` with a `CRLF`.

2. Why This Destroys Executables

In a text file, changing a line ending is harmless. But in an executable (`.exe`), every byte is compiled machine code.

- A byte containing `0x0A` (which is `LF` in text) might actually represent a critical processor instruction or part of a memory address in your program.
- If ASCII mode modifies that byte to `0x0D 0x0A` (`CRLF`), it **alters the binary code**, shifts the position of all subsequent data, and completely breaks the application.

Binary Mode Treats Data as Raw Bytes

When you switch to **`binary`** mode (also called Image mode), you tell FTP to turn off all translation features. It copies the file byte-for-byte exactly as it is, ensuring your executable arrives fully intact and functional.

## Use
For Disabling Passive Connection
`passive`

Then to transfer exe or img or zip use 
`binary`

Change to the local directory
`lcd /home/kali/Desktop`

Then to send it will be 
`put putty.exe`

To print the contents 
`get flag.txt -



