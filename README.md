Project Objective

The objective of this project is to identify and exploit a buffer overflow vulnerability in the brainpan.exe Windows application hosted on a TryHackMe machine, following the standard reverse-engineering and exploitation workflow.

🧪 Project Description

During the initial reconnaissance phase, a full port scan revealed an HTTP service running on port 10000. Directory enumeration identified a publicly accessible /bin/ directory containing the Windows executable brainpan.exe, which was downloaded for further analysis.

The binary was confirmed to be a Windows PE executable, indicating that reverse engineering and debugging must be performed in a Windows environment using tools such as Immunity Debugger and mona.py.

Since TryHackMe internal IP addresses are accessible only from within the VPN, the executable was first downloaded via the Linux AttackBox and then transferred to a local Windows system for analysis.

The planned exploitation workflow consists of:

debugging the application locally on Windows to identify a buffer overflow condition;

determining the exact offset to control the instruction pointer (EIP);

locating a suitable JMP ESP instruction;

crafting a malicious payload;

launching the final exploit from a Linux machine (Kali / AttackBox) to obtain remote code execution on the target system.

This approach follows the intended design of the Brainpan room, where Windows is used for binary analysis and Linux is used for exploitation.


📝 Project Note

During the execution of the Brainpan 1 room, the reconnaissance and service analysis phases were successfully completed, including the discovery and extraction of the vulnerable binary brainpan.exe.

However, further buffer overflow debugging requires a Windows-based environment with Immunity Debugger and proper network connectivity between the local Windows system and the TryHackMe virtual machine. At the time of execution, technical limitations related to networking and environment isolation prevented reliable interaction between the Windows debugging setup and the target machine.

As a result, the practical exploitation phase was paused at the environment preparation stage. Nevertheless, the exploitation workflow, required tools, and attack architecture were fully analyzed and documented.

