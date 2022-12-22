---
description: Lame box - walkthrough used approx. 60%
---

# Lessons Learned

* searchsploit vs msf>search
  * searchsploit is without Metasploit and helps me obtain a deeper understanding of how Metasploit exploits work.
* Try all vulnerabilities when one leads to a dead end (e.g. vsftpd has a vulnerability and exploit but not as exploitable the exploit for Samba 3.0.20).
  * I spent too much time on one vulnerability
  * Should've tried the obvious FTP anonymous login much sooner
* GitHub, YouTube, StackOverflow, Google - all good resources to get hints/tips without spoiling the box.
* Learned about smbclient and it's usage with netcat:
  * \-nvlp options are used to be numeric only, set listen mode for inbound connects, verbose, and local port number.
* Learned more about net cat, and it's usage with smbclient:
  * \-L to list all services
* Searchsploit -m to copy the exploit locally to be used later in the attack
* Learned more about how to use nano and vim text editors.
* Python scripts are fragile, and I need to understand more of this language.
