Windows 7 Penetration Testing Report:

This repository documents a penetration test performed on Windows 7 Home Premium SP1 in a controlled lab environment. The project demonstrates how both traditional exploit attempts and client-side attacks with social engineering can be used to compromise a target system.

📌 Objective

To gain unauthorized access to a Windows 7 system using ethical hacking techniques and demonstrate post-exploitation capabilities.

⚙️ Lab Setup

Target: Windows 7 Home Premium SP1 (192.168.1.6)

Attacker: Kali Linux (192.168.1.5)

Tools Used:

Nmap

Metasploit Framework

Msfvenom

Python HTTP Server

🔍 Methodology

Network Scanning

Identified target system using netdiscover and nmap.

Enumerated OS details, open ports, and services.

Vulnerability Assessment

Attempted exploitation of common Windows vulnerabilities (EternalBlue MS17-010, MS08-067, MS09-050).

System was patched against known SMB vulnerabilities.

Client-Side Attack (Successful)

Generated a malicious payload with msfvenom.

Hosted payload via Python HTTP server.

Delivered payload through social engineering (disguised as game.exe).

Gained access once the target executed the file.

Post-Exploitation

Established a Meterpreter session.

Retrieved system information and user privileges.

Captured a screenshot as proof of compromise.

Screenshots of exploitation and post-exploitation phases already uploaded in folder.

🚨 Disclaimer

This project was conducted strictly for educational purposes in a controlled environment.
Do not attempt these techniques on real systems without explicit authorization.
