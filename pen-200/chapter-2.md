---
description: Kali Linux
---

# Chapter 2

* created and managed by OffSec
* use 64 bit ISO image
  * change default password (gigs, bubb@69!)
* Sudo for elevated priviledges
* Kali menu shows applications that you can use
* Kali Documentation
  * use for research/study
    * https://docs.kali.org
    * https://forums.kali.org
    * https://tools.kali.org
    * https://bugs.kali.org
    * https://kali.training
* Linux File system:
  * **/bin/** - basic programs: ls, cd, cat
  * **/sbin/** - system programs: fdisk, mkfs, sysctl
  * **/etc/** - configuration files
  * **/tmp/** - temporary files, deleted on boot
  * **/usr/bin/** - applications: apt, ncat, nmap
  * **/usr/share/** - application support, data files
* Basic Linux commands:
  * **man** - man pages are formal documentation on a command
    * "  man -k '^passwd$'  " shows section from man pages
  * **apropos** - man page description based on a match of a keyword
    * "  apropos partition  " same function as "man -k"
  * **ls** - basic file listing
    * \-a : displays all files, -1 : displays on a single line > -a1
  * **cd** - change directory
    * cd \~ : home directory
  * **pwd** - print current director
  * **mkdir** - creates specified directory (do not use spaces unless wrapped in quotes)
    * use - or \_ instead of spaces
    * \-p option: creates parent directories, can be used for complex directory structure
  * **which** - searches in path directory varibale for a file name, returns full PATH to the file
  * **locate** - quickest to find location of files and directories in FS (file system). Locate searches locate.db, built in database updated regularly by cron scheduler.
  * **find** - more complex than locate and which. Can search for files and directories by more than just the name (age, size, owner, etc.)
* Services
  * **SSH** - secure shell used to remotely access a computer, TCP based, listens on port 22.
  * **HTTP** - apache http service, TCP based, listens on port 80.
* Installing/removing tools
  * **apt update** - updates list of available packages
  * **apt upgrade** - upgrade to latest versions after update (snapshot VM before)
  * **apt-cache search** - displays info in cache packaged db. output reveals application.
    * searches description
    * **apt show** - displays full application info
  * **apt install** - install packages
  * **apt remove --purge** - removes packages completely, apt remove removes all pacakge data but not user config options, purge removes all config files.
  * **dpkg** - install core package directly or indirectly through apt, does not install dependencies that the package may require. Preferred tool to install when offline.
    * **-i**  :  install option
*
