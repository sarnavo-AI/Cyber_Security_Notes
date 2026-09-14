==**WMIexec** is a remote administration and execution tool== (often used via scripts like Impacket's `wmiexec.py`) that leverages Windows Management Instrumentation (WMI) and DCOM to run commands on a remote computer. [[1](https://python.plainenglish.io/lateral-movement-with-python-remotely-executing-commands-over-smb-wmi-4fb95526b3d6), [2](https://www.crowdstrike.com/en-us/blog/how-to-detect-and-prevent-impackets-wmiexec/)]

---

Key Differences: WMIexec vs. PsExec

| Feature                  | WMIexec (`wmiexec.py`)                                                                                              | PsExec (`psexec` / `psexec.py`)                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Underlying Mechanism** | Uses **WMI** and **DCOM** (RPC port 135 to initiate, random high ports for communication, and SMB to fetch output). | Uses **SMB** (port 445) to upload and install a temporary service binary (`PSEXESVC.exe`).                                  |
| **Service Creation**     | **Does not** create a remote Windows service or drop executable binaries on the target disk.                        | **Creates** a temporary Windows service and drops an executable binary into the `ADMIN$` share (`C:\Windows`).              |
| **Privilege Level**      | Executes commands in the context of the authenticated local/domain administrator.                                   | Typically elevates and runs commands as **`NT AUTHORITY\SYSTEM`** (the highest local privilege).                            |
| **Output Handling**      | Redirects command output to a temporary text file in an SMB share (`ADMIN$`), reads it, and deletes the file.       | Establishes full-duplex, real-time interactive communication channels using **named pipes** (`RemCom_stdin`, etc.).         |
| **Detection Footprint**  | Quieter regarding service-creation event logs, but generates DCOM/WMI and share-access network traffic.             | Noisier on disk and in event logs due to dropping binaries and installing services, but heavily monitored by EDR solutions. |
