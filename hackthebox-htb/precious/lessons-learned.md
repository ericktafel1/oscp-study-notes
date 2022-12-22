---
description: Precious box - walkthrough used...
---

# Lessons Learned

* OSINT tools are so important. Be more patient and more precise when searching for vulnerabilities and exploits on the internet. Don't give up and TRY HARDER.
* Start the server 8080 if port 80 is an open port to view in browser
* Downloaded exiftool - this shows pdf/document details. Used this to find creator exploits
* Bash script for command injection was added from a web browser extension from walkthrough referenced.
  * 2>/dev/null = added and redirects the output to a file (2> redircts stderr to file)
* $ ls -lhRa = lists credentials and ./bundle is read to find more info.. ./bundle because it has the config file in it as shown from this command.
  * \-lh = list files and directories in human readabile format. -R = lists contents recursively, lists files together with the contents of the directories present in the path, -a = lists all entries, entries that being with a "."
* ssh as user using config info from bundle.
* As henry user, reading updated.dependencies.yml can help us find a vulnerability + exploit to get root access.
* Updating git\_set to allow access using the command injection exploit found for ruby yaml rce
* $ sudo /usr/bin/ruby /opt/update\_dependencies.rb 2>/den/null = gets use to root access... by runnning the new dependencies updated with command injection above (and changing git\_set)
