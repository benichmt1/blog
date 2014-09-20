---
layout: post
title: "ant os family list values"
description: "ant os family list values"
category: ant
tags: [ant]
---
{% include JB/setup %}
##os

Test whether the current operating system is of a given type. Each defined attribute is tested and the result is true only if all the tests succeed.

Attribute   Description Required       
family  The name of the operating system family to expect.  No       
name    The name of the operating system to expect. No       
arch    The architecture of the operating system to expect. No       
version The version of the operating system to expect.  No       

<!-- more -->

###Supported values for the family attribute are:       

* `windows` (for all versions of Microsoft Windows)
* `dos` (for all Microsoft DOS based operating systems including Microsoft Windows and OS/2)
* `mac` (for all Apple Macintosh systems)
* `unix` (for all Unix and Unix-like operating systems)
* `netware` (for Novell NetWare)
* `os/2` (for OS/2)
* `tandem` (for HP's NonStop Kernel - formerly Tandem)
* `win9x` for Microsoft Windows 95 and 98, ME and CE
* `winn`t for Microsoft Windows NT-based systems, including Windows 2000, XP and successors
* `z/os` for z/OS and OS/390
* `os/400` for OS/400
* `openvms` for OpenVMS

