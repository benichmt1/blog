---
layout: post
title: "How to format data from the file usb.ids to the file 51 android.rules"
description: "How to format data from the file usb.ids to the file 51 android.rules"
category: android
tags: [linux,android]
---
{% include JB/setup %}

1.Download the file usb.ids from http://www.linux-usb.org/usb.ids
{% highlight bash %} 
wget -c http://www.linux-usb.org/usb.ids
{% endhighlight %}
<!-- more -->

2.Delete the other section from the file usb.ids but "Vendors, devices and interfaces".
{% highlight xml %} 
0001  Fry's Electronics
	142b  Arbiter Systems, Inc.
	7778  Counterfeit flash drive [Kingston]
0002  Ingram
0003  Club Mac
0004  Nebraska Furniture Mart

...

eb2a  KWorld
f003  Hewlett Packard
	6002  PhotoSmart C500
f4ec  Atten Electronics / Siglent Technologies
	ee38  Digital Storage Oscilloscope
{% endhighlight %}

3.use sed to delete other unuseful section.
{% highlight bash %} 
sed  -i '/^#/d' usb.ids 
sed  -i '/^   /d' usb.ids 
{% endhighlight %}
The second param like space is:
a. press CTRL+V
b. press TAB

4.format data to the file 51 android.rules
{% highlight bash %} 
gawk 'BEGIN{FS="  ";OFS="\t"}{print "#"$2" \012SUBSYSTEM==\"usb\", ATTRS{idVendor}==\""$1"\", MODE=\"0660\", GROUP=\"plugdev\"\012"}' usb.ids > 51-android.rules 
{% endhighlight %}

5.add the header
{% highlight xml %} 
###################################################### 
#  Project:  https://github.com/snowdream/51-android #
#  File:     /etc/udev/rules.d/51-android.rules      #
#  Author:   snowdream <yanghui1986527@gmail.com>   #
#  Date:     2014.05.25                              #
######################################################
{% endhighlight %}

That's All.
