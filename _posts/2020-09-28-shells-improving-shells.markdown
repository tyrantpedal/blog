---
layout: post
title:  "Improving Shells"
date:   2020-09-28 01:00:32 -0800
author: andy
categories: shells
tags: shells
---
* * *

Many times when gaining access to a target the shell we end up with is very limited and can make it difficult (sometimes impossible) to work.  Below are some ways to improve a limited shell.

### Python (if available on the target)

***Python one-liner***
- `python -c 'import pty;pty.spawn("/bin/bash")'`

***Python PTY Shells***

To get a full pty shell, Darren 'infodox' Martyn has put together some great shells [here](https://github.com/infodox/python-pty-shells){:target="_blank"}