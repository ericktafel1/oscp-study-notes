---
description: Command Line Fun
---

# Chapter 3

* **Bash** - shell that allows complex commands and different tasks froma  terminal window. incorporates useful features from a **KornShell**  and **C Shell**
* **Environment variables -** form of global storage for various settings inherited by any applications run during that terminal sessions. (e.g. **$PATH**)
  * echo $PATH
  * echo $USER
  * echo $PWD
  * echo $HOME
  * define an Environment Variable using the **export** command
  * **env -** lists predefined environment variables
* Bash has Tab Completions, used to autofill file names/directory paths
* Bash History Tricks
  * **history** - command to display commands used!
    * to rerun a command, type "!" followed by line number
    * **!!** repeats last command executed.
    * saved to **bash\_history** file
    * **$HISTSIZE** controls # of commands stored for current session
    * **$HISTFILESIZE** how many commands are kept in the **bash\_history** file.
    * up arrow scrolls backwards in history, down arrow forward
    * **CTRL + R** is the reverse-i-search, search recent command that contains a letter
  * Piping and Redirection
    * Standard Input (STDIN) - data fed into program
    * Standard Output (STDOUT) - output from the program (defaults to terminal)
    * Standard Error (STDERR) - error messages (defaults to terminal)
    * Piping = " | "
    * Redirection = " > "
    * Redirecting
      * " **>** " can save output to a file
      * no undo function, can replace original data
      * **>>** is used to append additional data to an exisint file, does NOT overwrite data
      * " **<** " can redirect input from a file to a command:
        * e.g. "wc -m < redirection\_test.txt" -------- 89
          * wordcount command receives input from .txt and results 89
      * STDERR
        * 0,1,2
        * "**2>**" corresponds to standard error and redircts error message
          * e.g. "ls ./test 2>error.txt"
    * Piping
      * " **|** "&#x20;
        * e.g. "cat error.text | wc -m > count.txt"
* Text searching/manipulation
  * **grep** - searches text files for the occurrence of a given expression
    * e.g. "ls -la /usr/bin | grep zip" searches /usr/bin for any line containing zip\\
  * **sed** - powerful stream editor, text editing on a stream of text.
    * e.g. "    echo "I need to try hard" | sed 's/hard/harder/'     "
      * substitutes hard for harder
  * **cut** - used to extract a section of text from a line and output to STDOUT
    * \-f for field # we are cutting
    * \-d to define field delimiter
  * **awk** - programming language designed for text processing, used as a data extraction and reporting tool. Like **cut** but more flexible
    * \-F is the field separator
    * e.g. "   echo "hello::there::friend" | awk -F "::" '{print $1, $3}'   " ----- displays "hello friend"
* Editing files from command line
  * **nano** - most simple, make any changes like a graphical, menu at bottom
    * **CTRL + O** - write changes
    * **CTRL + K** - Cut a line
    * **CTRL + U** -  Paste cut line
    * **CTRL + W** - search within file
    * **CTRL + X** - to exit
  * **vi** - fast and complex text editor, not as simple as nano
    * "i" - enable insert text mode&#x20;
      * **ESCAPE** to go back to command mode
    * "dd" - delete current line
    * "yy" - copy current line
    * "p" - paste clipboard contents
    * "x" - delete character under cursor
    * ":w" - write current file to disc and remain in vi
    * ":q!" - to quit without writing the file to the disk
    * ":wq!" to save the file and quit vi
* Comparing Files
  * **comm** - compares two text files, displaying unique and common lines. 3 spaced offeset columns, 1st unique to first file, 2nd unique to second file, 3rd are shared between the files
    * **-n** switch can suppress 1 or more columns&#x20;
  * **diff** - detect differences between files, similar to comm but more complex supporting many diff output formats: **context** & **unified**
    * **-c** displays in context format
    * **-u** displays in unified format
  * **vimdiff** - extended version of vi. two files in one window and highlights differences
    * **CTRL + W >(arrow key)** - switch between windows
    * **]C** - next change in diff
    * **\[C** - previous change
    * **D + O** - change from other window and put it in current
    * **D + P** - change from current window and put it in other
    * :q! - to quit **vimdiff,** same shortcuts as **vi**
* Managing Processes
  * process is assigned an ID (PID)
  * background (**bg**) processes, append at end of command with **&** to send to background
    * foreground (**fg**) uses terminal for the job, must wait or use CTRL + C to cancel to use terminal again
  * **jobs** and **fg**
    * **jobs -** lists the jobs running in the current terminal session
    * **fg %**(job #) - shows jobs running in the fg terminal
    * **fg -** to return the job to the foreground, can also reference using PID or Job #
  * **ps** and **kill**
    * **ps** - process status, lists processes system wide not just the terminal.&#x20;
      * **-ef** - e selects process, f for full format listing
      * **-fC** - specific command name and full format
    * **kill** - stop process without using the GUI. Must know the PID
* File and Command Monitoring
  * **tail** - monitor long file entries as they are being written, displays end of file or most recent entries.
    * **-f** - continuously updates the output as the file target grows
    * **-n#** - outputs number of lines specified
  * **watch** - used to run a command at intervals (default every 2s)
    * **-n#** - runs at # of seconds specified
* Downloading Files
  * **wget** - downloads files using HTTP and FTP protocols
    * **-O** - to save under a different name on local machine
  * **curl** - tool to transfer data to or from a server. Basic use is similar to **wget**
    * **-o** - to specify output file name
  * **axel** - download accelrator, transfers a file form HTTP or FTP server through multiple connections
    * **-n** - specifies number of multiple connections to use
    * **-a** - for more precise progress indicator
    * **-o** - to specify a different file name for the download
* Customizing the Bash Environment
  * Bash History
    * **HISTCONTROL** - defines whetehr or not to remove duplicate commands
    * **HISTIGNORE** - filters basic commands that are run frequently (ls, history, exit, etc.)
    * **HISTTIMEFORMAT**- controls date/time stamps in output of the history command.
  * **Alias** - string we can define to replace commonly used commands or switches (command we define built by other commands)
    * "alias lsa='ls -la' "
  *   Persistent Bash Customization

      * /etc/bash.**bashrc** - file that is system-wide for bash customization
      * setup in user's home directory, executed every login session



