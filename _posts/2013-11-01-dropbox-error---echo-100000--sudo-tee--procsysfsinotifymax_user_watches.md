---
layout: post
title: "Dropbox error   'echo 100000 | sudo tee / proc/sys/fs/inotify/max_user_watches'"
description: "box error   'echo 100000 | sudo tee / proc/sys/fs/inotify/max_user_watches"
category: other
tags: [dropbox]
---
{% include JB/setup %}

Monitoring more than 10000 folders

The Linux version of the Dropbox desktop application is limited from monitoring more than 10000 folders by default. Anything over that is not watched and, therefore, ignored when syncing. There's an easy fix for this. Open a terminal and enter the following:
{% highlight bash %}
echo fs.inotify.max_user_watches=100000 | sudo tee -a /etc/sysctl.conf; sudo sysctl -p
{% endhighlight %}
This command will tell your system to watch up to 100000 folders. Once the command is entered and you enter your password, Dropbox will immediately resume syncing.

Reference:         
1、[Dropbox error - 'echo 100000 | sudo tee / proc/sys/fs/inotify/max_user_watches'][1]


[1]:http://askubuntu.com/questions/148171/dropbox-error-echo-100000-sudo-tee-proc-sys-fs-inotify-max-user-watches?answertab=active#tab-top
