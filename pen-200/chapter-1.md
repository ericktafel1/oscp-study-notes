---
description: General Course Information
---

# Chapter 1

* PwK was created for Sys and Network Admins
* Access PwK VPN Lab Network
* [https://forums.offensive-security.com/](https://forums.offensive-security.com/)
  * Forum for students
* [https://chat.offensive-security.com/](https://chat.offensive-security.com/)
  * live support
* Included in PEN-200 is OSCP Exam attempt
* Recommended strategy
  1. Review all the information included in the resources provided after the registration process.
  2. Review the course materials.
  3. Complete all the course exercises.
  4. Attack the lab machines.
     1. check student forums if struggling
     2. check hints
* A **penetration test** is an ongoing cycle of research and attack against a target or boundary. The attack should be structured, calculated, and, when possible, verified in a lab before being implemented on a live target. This is how we visualize the process of a penetration test:

<figure><img src="https://offsec-platform-prod.s3.amazonaws.com/offsec-courses/PEN-200/imgs/intro/bddc32b581ac729a654e931b8cc762d5-00-01.png" alt=""><figcaption></figcaption></figure>

* MegaCorpone.com and Sandbox.local Domains are **FICTITIOUS** created by OffSec
* **add new user (preferred) OR change default passwords** on Lab machines
* 12x reverts allowed per 24h - **revert** at start of scan and attack & once you are done with the machine
* **Create** a directory to store exploits. **Delete** when done with machine & revert.
* Recommended ssh command for Topic Exercises:

{% code overflow="wrap" %}
```
ssh -o "UserKnownHostsFile=/dev/null" -o "StrictHostKeyChecking=no" student@192.168.50.52 -p 2222
```
{% endcode %}

* The _UserKnownHostsFile=/dev/null_ and _StrictHostKeyChecking=no_ options have been added to prevent the **known-hosts** file on our local Kali machine from being corrupted.
* **Reporting**
  * What did you set out to accomplish? Is there a single, specific statement you hope to make in the report? We highly recommend writing an outline before starting. You can do this quickly and easily by creating section headers, without the actual content or explanation.
  * What does your audience hope to learn from it? Who are they? Most reports start with an Executive Summary. The Executive Summary should be a short (no more than two pages), high-level explanation of the results and the client's overall security posture.
  * DO NOT include pages and pages of a tool output in your report unless it is absolutely relevant. If you have a point that you are trying to make, for example a very high number of SNMP services exposed on publicly accessible hosts, then use the –oG flag and grep out only those hosts with open SNMP ports.
  * Use a screenshot to make a point, not just to show awesome meterpreter output. Consider providing additional supporting documents in addition to the report.
  * Refer back to the objective of the assessment.
  * Be consistent. Spellcheck.
  * [https://help.offensive-security.com/hc/en-us/articles/360046787731-Penetration-Testing-with-Kali-Linux-Reporting](https://help.offensive-security.com/hc/en-us/articles/360046787731-Penetration-Testing-with-Kali-Linux-Reporting)
    * Report Templates
  * Taking Notes:
    * be detailed, document everything
    * use rough templates/formats for notes that resemble the report.
    * backup/encrypt notes
    * OneNote[1](https://portal.offensive-security.com/courses/pen-200/books-and-videos/modal/modules/penetration-testing-with-kali-linux-general-course-information/reporting/taking-notes#fn1) (Windows/macOS), DayOne[2](https://portal.offensive-security.com/courses/pen-200/books-and-videos/modal/modules/penetration-testing-with-kali-linux-general-course-information/reporting/taking-notes#fn2) (macOS) or Joplin[3](https://portal.offensive-security.com/courses/pen-200/books-and-videos/modal/modules/penetration-testing-with-kali-linux-general-course-information/reporting/taking-notes#fn3) (MacOS/Windows/Linux) etc. You can also opt to use something like MDwiki,[4](https://portal.offensive-security.com/courses/pen-200/books-and-videos/modal/modules/penetration-testing-with-kali-linux-general-course-information/reporting/taking-notes#fn4) a markdown-based wiki that allows you to write in markdown and then render the output in HTML.
    * The best way to go about collecting RAW output is to set up some type of logging. This way the output is automatically saved and you do not have to worry about remembering to return to your notes. There are a few ways for all output displayed to a terminal to be saved, some of which include:
      * _**script**_: Once executed, all output (including bash's color & backspaces) is saved to a file, which can be replayed at any time.
      * _**terminator**_: An alternate terminal emulator that has various features and plugins, such as Logger (save all output to a text file) and TerminalShot (take a screenshot from within the terminal).
      * **NOTE**: Piping the output (>) or using tee is also an option, but you have to use them for each command, so you will have to remember to run them every time.
* Exam
  * 23h, 45m
  * need 70 points + report (24h to submit after exam ends)
  * 10 bonus points - 80% exercises, 30 proof text from lab machines
  * results within 10 business days
  * Use Metasploit in labs but on exam can only use for one machine
  *
