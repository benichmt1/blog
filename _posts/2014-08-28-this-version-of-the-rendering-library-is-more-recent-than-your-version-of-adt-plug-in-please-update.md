---
layout: post
title: "[转载]This version of the rendering library is more recent than your version of ADT plug in. Please update"
description: "This version of the rendering library is more recent than your version of ADT plug in. Please update"
category: android
tags: [android]
---
{% include JB/setup %}

地址：http://stackoverflow.com/questions/18852983/eclipse-reports-rendering-library-more-recent-than-adt-plug-in

预览layout.xml文件时提示：  
This version of the rendering library is more recent than your version of ADT plug-in. Please update ADT plug-in  
导致无法正常预览布局文件；    
问题根源：SDK版本过高，ADT版本低；   
<!-- more -->

解决办法有好几种，如下：

1.Click Help > Install New Software. 
In the Work with field, enter: https://dl-ssl.google.com/android/eclipse/     
Select Developer Tools / Android Development Tools.   
Click **Next** and complete the wizard.      

2.Change android version while rendering layout.

![20140302144122656.png]({{ BASE_PATH }}/assets/images/20140302144122656.png)

3.Change the Target version to new updates you have. Otherwise, change what SDK version you have in the Android manifest file.