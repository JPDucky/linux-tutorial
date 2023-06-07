Simon's Learning Plan
=====================
## 1. Introduction
### 1.1. Linux
#### 1.1.1. Linux Basics
##### 1.1.1.1 Linux File System
The file systems on Linux are very different from the file systems that Windows uses. The most important difference is that Linux does not have a concept of drive letters. Instead, all file systems are mounted into one big tree, with the root (/) at the top. This means that all files and directories appear under the root directory, even if they are stored on different devices.

Your user file are located in the `/home` directory. The `/home` directory contains a subdirectory for each user. For example, if your username is `simon`, your home directory is `/home/simon`. This directory is often referred to as `~` (tilde). You can use `~` to refer to your home directory. For example, if you want to go to your home directory, you can type `cd ~` in the terminal. You can also use `~` in paths. For example, if you want to go to the `Documents` directory in your home directory, you can type `cd ~/Documents` in the terminal. 

The `/home` directory is also referred to as `$HOME` in the terminal. You can use `$HOME` to refer to your home directory. For example, if you want to go to your home directory, you can type `cd $HOME` in the terminal. You can also use `$HOME` in paths. For example, if you want to go to the `Documents` directory in your home directory, you can type `cd $HOME/Documents` in the terminal.

The `/etc` directory contains configuration files. The `/etc` directory contains a lot of files and directories. Many of the programs on linux will put their  configuration files within the `/etc` directory. For example, the `/etc/ssh` directory contains the configuration files for the SSH server. The `/etc/ssh` directory contains a file called `sshd_config`. This file contains the configuration for the SSH server. You can view the contents of this file by typing `cat /etc/ssh/sshd_config` in the terminal. You can also edit this file by typing `sudo nano /etc/ssh/sshd_config` in the terminal. The `sudo` command is used to run a command as another user, usually the root user. The `nano` command is a text editor. You can use the `nano` command to edit text files. You can find more information about the `nano` command by typing `man nano` in the terminal.

The `/usr` directory stands for "unix system resources" (NOT user!!). Many of the programs on linux will put their files within the `/usr` directory. For example, the `/usr/bin` directory contains the executable files for the programs on linux. The `/usr/bin` directory contains a file called `nano`. This file contains the executable for the `nano` command. You can view the contents of this file by typing `cat /usr/bin/nano` in the terminal. You can also run this file by typing `/usr/bin/nano` in the terminal. You can find more information about the `nano` command by typing `man nano` in the terminal.
- an important thing to note about about the `/usr` directory is that it is where your package manager (in our case `apt`) puts the programs it installs (e.g. `apt install chromium-browser` will install the chromium browser in `/usr/bin/chromium-browser`). 
- The programs in `/usr/bin` and `/usr/local/bin` are available to all users on the system.
- The programs in `/usr/sbin` and `/usr/local/sbin`are available to the root user on the system.
- The system will check for a programs configuration files in the `/usr` directory first. This is where the "defaults" of a package are stored. Note that if you have a configuration file in the `/etc` directory, the system will use that configuration file instead of the one in the `/usr` directory, and likewise if there is a configuration in your home directory, the system will use that configuration file instead of the one in the `/etc` directory.
    - This happens because configurations are loaded in the following order:
        1. `/usr`
        2. `/etc`
        3. `$HOME` or `~` or `/home/<user>`
        - What this translates to is your user's configuration files will override the system's configuration files, which will override the package's configuration files.

The `/var` directory stands for "variable". Many of the programs on linux will put their files within the `/var` directory. For example, the `/var/log` directory contains the log files for the programs on linux. The `/var/log` directory contains a file called `auth.log`. This file contains the log for the authentication process. You can view the contents of this file by typing `cat /var/log/auth.log` in the terminal. You can also edit this file by typing `sudo nano /var/log/auth.log` in the terminal. The `sudo` command is used to run a command as another user, usually the root user. The `nano` command is a text editor. You can use the `nano` command to edit text files. You can find more information about the `nano` command by typing `man nano` in the terminal.
##### 1.1.1.2 Linux Commands
###### 1.1.1.2.1 Bash
The most common shell in Linux is the Bash shell. Bash is an acronym for Bourne Again Shell. It is the default shell for most Linux distributions. Bash is a superset of the Bourne shell (sh), and includes many features of other shells such as the C shell (csh) and Korn shell (ksh). Bash is a command processor that typically runs in a text window where the user types commands that cause actions. Bash can also read commands from a file, called a script. Like all Unix shells, it supports filename wildcarding, piping, here documents, command substitution, variables, and control structures for condition-testing and iteration. The keywords, syntax, dynamically scoped variables and other basic features of the language are all copied from sh. Other features, e.g., history, are copied from csh and ksh. Bash is a POSIX-compliant shell, but with a number of extensions.

I have set you up with ZSH, which is very similar to bash, but has more features. I have also installed Oh My ZSH, which is a framework for managing your ZSH configuration. It comes bundled with a ton of helpful functions, helpers, plugins, themes, and a few things that make it more visually appealing, etc.

Below you can find a list of some of the most common commands used in the terminal. You can find more information about each command by typing `man <command>` in the terminal. For example, `man ls` will give you more information about the `ls` command:
- `echo` - display a line of text
- `printf` - format and print data
- `cat` - concatenate files and print on the standard output (combine files and print on the next line of the terminal)
- `ls` - list directory contents
- `cd` - change the working directory
- `pwd` - print name of current/working directory
- `mkdir` - make directories
- `rmdir` - remove empty directories
- `touch` - change file timestamps or create a new empty file
- `cp` - copy files and directories
- `mv` - move (rename) files
- `rm` - remove files or directories
- `ln` - make links between files
- `find` - search for files in a directory hierarchy
- `grep` - print lines matching a pattern
- `wc` - print newline, word, and byte counts for each file
- `sort` - sort lines of text files
- `cut` - remove sections from each line of files
- `sed` - stream editor for filtering and transforming text
- `awk` - pattern scanning and processing language
- `tar` - an archiving utility
- `zip` - package and compress (archive) files
- `unzip` - list, test and extract compressed files in a ZIP archive
- `gzip` - compress or expand files
- `gunzip` - compress or expand files
- `zcat` - compress or expand files
- `ping` - send ICMP ECHO_REQUEST to network hosts
- `traceroute` - print the route packets trace to network host
- `netstat` - print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
- `ifconfig` - configure a network interface
- `route` - show / manipulate the IP routing table
- `ssh` - OpenSSH SSH client (remote login program)
- `scp` - secure copy (remote file copy program)
- `wget` - The non-interactive network downloader
- `curl` - transfer a URL
- `telnet` - user interface to the TELNET protocol
- `whois` - client for the whois directory service
- `dig` - DNS lookup utility
- `host` - DNS lookup utility
- `nslookup` - query Internet name servers interactively
- `lsof` - list open files
- `ps` - report a snapshot of the current processes
- `kill` - send a signal to a process
- `killall` - kill processes by name
- `bg` - lists stopped or background jobs; resume a stopped job in the background
- `fg` - brings the most recent job to foreground
- `jobs` - lists stopped or background jobs
- `nohup` - run a command immune to hangups, with output to a non-tty
- `top` - display Linux processes
- `uptime` - show how long system has been running
- `free` - Display amount of free and used memory in the system
- `df` - report file system disk space usage
- `du` - estimate file space usage
- `mount` - mount a file system
- `umount` - unmount file systems
- `useradd` - create a new user or update default new user information
- `usermod` - modify a user account
- `userdel` - delete a user account and related files
- `groupadd` - create a new group
- `groupmod` - modify a group definition on the system
- `groupdel` - delete a group
- `passwd` - update a user's authentication tokens(s) (password)
- `chage` - change user password expiry information
- `chown` - change file owner and group
- `chmod` - change file mode bits (permissions)
- `su` - change user ID or become superuser (switch user)
- `sudo` - execute a command as another user (superuser-do)
- `chroot` - run command or interactive shell with special root directory
- `uname` - print system information (kernel version)
- `date` - print or set the system date and time
- `cal` - displays a calendar and the date
- `echo` - display a line of text
- `hostname` - show or set the system's host name
- `whoami` - print effective userid
- `who` - show who is logged on
- `last` - show a listing of last logged in users
- `lastlog` - reports the most recent login of all users or of a given user
##### 1.1.1.3 Linux Shell Scripting
