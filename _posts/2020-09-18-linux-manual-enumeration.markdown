---
layout: post
title:  "Linux Enumeration"
date:   2020-09-17 15:22:32 -0700
author: andy
categories: linux
tags: linux
---

These assume you already have a limited shell on the target

### System Enumeration
 
- `hostname` # displays the system hostname
- `uname -a` # architecture (cores and stuff) 
- `lscpu`  # architecture (cores and stuff)
- `cat /etc/issue` # distro
- `cat /proc/version` # kernel version and architecture
- `ps aux` # services running (can grep by user, service, etc)

### User Enumeration

- `whoami` # displays username for the current user
- `id` # displays user id and group id's for the current user
- `sudo -l` # shows what the current user can do with sudo
- `cat /etc/passwd` # lists out accounts on the system (no passwords!)
- `cat /etc/passwd | cut -d : -f 1` # will give us just the usernames from the /etc/passwd file
- `cat /etc/shadow` # this is where the passwords are, but likely you will not have access to read this fill as a non-root user
- `cat /etc/group` # lists groups
- `history` # lists the history of commands the user has recently used
- `sudo su -` # to sudo into the root user

### Network Enumeration

- `ifconfig` # displays network interface information (older systems)
- `ip a` # displays network interface information (newer systems)
- `route` # displays route information (older systems)
- `ip route` # displays route information (newer systems)
- `arp -a` # displays arp info (older systems)
- `ip neigh` # displays arp info (newer systems)
- `netstat -ano` # displays ports and ip's connected

### Password Enumeration

**Password Hunting**

- `grep --color=auto -rnw '/' -ie "PASSWORD" --color=always 2>/dev/null` # searches the entire file system for the word **password** and will color highlight
- `locate password | more` # display files with the word "password" in the file name
- `find / -name authorized_keys 2>/dev/null` # searches the entire file system for files named "authorized_keys"
- `find / -name id_rsa 2>/dev/null` # searches the entire file system for files named "id_rsa"

