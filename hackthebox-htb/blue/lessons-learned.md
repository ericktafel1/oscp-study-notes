---
description: Blue box - walkthrough used after enumeration
---

# Lessons Learned

* Nmap - learning more about options to use with the target IP address
  * \-sVC 10.10.10.40 for a more verbose result of listening ports
  * \--script=\*smb-vuln\* -p139,445 for identified vulnerabilities in the identified listening ports. This option I was unfamiliar with more so than -sVC.
* Learned about Searchsploit and how to use
  * Searchsploit is used to search for exploits and related data in the exploit database (Exploit-DB). It uses shell scripts to parse through data from the CSV files from the repository. In this case, we found ms17-010 identified in the nmap smb-vuln results above and can search exploits for this vulnerability.
* Learned about search command in msfconsole and find it more useful as it has the direct exploit ready to call upon in msfconsole.
* Metasploit - use exploit/windows/smb/ms17\_010\_eternalblue which was identified in the searchsploit results
  * set LHOST to ifconfig > tun0 > inet
  * set rhost to 10.10.10.40
  * check settings with options command
    * run command continued to fail because my Kali linux was not listening on the specified port of 4444 from the msf EternalBlue exploit. Connection was hanging at "\[\*] 10.10.10.40:445 - Triggering free of corrupted buffer.", however, eventually it worked.
  * 'whoami' did not work at the C:\ directory, but instead the 'shell' command allowed completion of the whoami command.
    * shell command sent me to the user haris directory where I could successfully execute whoami









