---
layout: post
title: "How to install and config git on Windows7"
description: "How to install and config git on Windows7"
category: windows
tags: [windows, git, gradle, android]
---
{% include JB/setup %}

##Problem
when i import the project [android-books][1] into intellij idea on window7,I get the error as follows:    
{% highlight bash %}
unexpected token: }
@ line 243, column 5.
{% endhighlight %} 
Then i guess it because the file build.gradle in the module app contains kroean or other characters, and i am using the windows 7(Chinese) with GBK.
<!-- more -->  

##Solution
Change the file.encoding to UTF-8.    
You can do this by setting `-Dfile.encoding=UTF-8` to the `GRADLE_OPTS` environment variable, or by adding `systemProp.file.encoding=UTF-8` to `gradle.properties`.

That is it,Enjoy it.

[1]: https://github.com/snowdream/android-books
