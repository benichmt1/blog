---
layout: post
title: "How to set sublime Text 3 as the default editor for the plain text file"
description: "How to set sublime Text 3 as the default editor for the plain text file"
category: sublime text 3
tags: [sublime text 3]
---
{% include JB/setup %}

If you install sublime text 3 in linux,like CentOS 7,and you want to set sublime Text 3 as the default editor for the plain text file,Please follow my steps.

##DownLoad And Install it
*  Download it from the website [http://www.sublimetext.com/3](http://www.sublimetext.com/3)
     * [Linux 64 bit](http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3065_x64.tar.bz2)  
     * [Linux 32 bit](http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3065_x32.tar.bz2)
*  Unzip it 
{% highlight bash %} 
tar jxvf sublime_text_3_build_3065_x64.tar.bz2
{% endhighlight %}
<!-- more -->

*  Config it
Open the file **sublime_text.desktop**,and set the right path for `Exec`,then save it.     
This is my file **sublime_text.desktop**:

{% highlight bash %} 
[Desktop Entry]
Version=1.0
Type=Application
Name=Sublime Text
GenericName=Text Editor
Comment=Sophisticated text editor for code, markup and prose
Exec=/home/snowdream/bin/sublime_text_3/sublime_text %F
Terminal=false
MimeType=text/plain;
Icon=sublime-text
Categories=TextEditor;Development;
StartupNotify=true
Actions=Window;Document;

[Desktop Action Window]
Name=New Window
Exec=/home/snowdream/bin/sublime_text_3/sublime_text -n
OnlyShowIn=Unity;

[Desktop Action Document]
Name=New File
Exec=/home/snowdream/bin/sublime_text_3/sublime_text --command new_file
OnlyShowIn=Unity;
{% endhighlight %}

##set the default editor for the plain text file (For Current User)
*  Open the dir **~/.local/share/applications**
*  Copy **sublime_text.desktop** here
*  Edit **defaults.list**, add the following text at the last line.
{% highlight bash %} 
text/plain=sublime_text.desktop
{% endhighlight %}
*  Save it.

##set the default editor for the plain text file (For All User)
*  Open the dir **/usr/share/applications**
*  Copy **sublime_text.desktop** here
*  Edit **defaults.list**, search **text/plain**,and replace 
{% highlight bash %} 
text/plain=gedit.desktop
{% endhighlight %}
to
{% highlight bash %} 
text/plain=sublime_text.desktop
{% endhighlight %}
*  Save it.

That's all,enjoy it.
