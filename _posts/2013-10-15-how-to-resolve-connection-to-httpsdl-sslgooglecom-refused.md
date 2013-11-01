---
layout: post
title: "how to resolve “Connection to https://dl ssl.google.com refused”?"
description: "how to resolve “Connection to https://dl ssl.google.com refused”?"
category: android
tags: [android studio, tools]
---
{% include JB/setup %}

If you download something from https://dl-ssl.google.com/  
For example:  
Download the lastest build for Android Studio:  
[https://dl-ssl.google.com/android/studio/ide-zips/0.2.13/android-studio-ide-132.863010-linux.zip](https://dl-ssl.google.com/android/studio/ide-zips/0.2.13/android-studio-ide-132.863010-linux.zip),  
you may get the errors"Connection to https://dl ssl.google.com refused".Why?
<!-- more -->

But you can download the Android Studio from the office url successful.   
[http://dl.google.com/android/studio/android-studio-bundle-130.737825-linux.tgz](http://dl.google.com/android/studio/android-studio-bundle-130.737825-linux.tgz)

Compare the two urls,You will get the new url for the lastest build for Android Studio:     
[http://dl.google.com/android/studio/ide-zips/0.2.13/android-studio-ide-132.863010-linux.zip](http://dl.google.com/android/studio/ide-zips/0.2.13/android-studio-ide-132.863010-linux.zip)  

Attention:  
1.change the "https" to "http";
2.change the "dl-ssl" to "dl";
3.keep other unchanged.

That's all, Good Luck!
