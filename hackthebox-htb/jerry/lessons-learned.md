---
description: Jerry box - walkthrough used
---

# Lessons Learned

* Begin all penetration tests with enumeration actions (nmap, masscan, etc.).&#x20;
  * masscan is a bulk scan looking for listening ports
  * nmap is a more verbose scan but takes a little longer
    * use nmap options such as:
      * \-sC : equivalent to --script=default
      * \-sV : Probe open ports to determine service/version info
      * \-oA : Output in the three major formats at once
* Attempt to connect to the web server in the VM before following the walkthrough. I began by following the walkthrough and didn't think to check 10.10.10.95:8080 and feel stupid as I spent a lot of time trying to make the python script work to brute force the Manager App.&#x20;
* Learned how to create payloads using msfvenom
  * \-p is set to specify it is a payload command
* Learned how to use nc command to listen to the port specified in the .war payload that I generated using msfvenom. Successful /shell link created in the Manager App
  * \-lvp is set to listen mode for inbound connects, verbose, and local port number
* Learned how to use Metasploit:
  * use command to navigate to the tomcat manager upload http.
  * set the http password and username, rhosts, rport, lhost, and run.
