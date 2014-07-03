---
layout: post
title: "${renderscript.opt.level} is not a permitted value for com.android.ant.RenderScriptTask$OptLevel"
description: "${renderscript.opt.level} is not a permitted value for com.android.ant.RenderScriptTask$OptLevel"
category: android
tags: [ant, android]
---
{% include JB/setup %}

##Problem
when i use ant to compile my android project,i get the error as follows:  
{% highlight bash %}
BUILD FAILED
D:\android-sdk-windows\sdk\tools\ant\build.xml:653: The following error occurred while executing this line:
D:\android-sdk-windows\sdk\tools\ant\build.xml:679: '${renderscript.opt.level}' is not a permitted value for com.android.ant.RenderScriptTask$OptLevel

Total time: 1 second
{% endhighlight %} 
<!-- more -->  

##Solution
Write the following code in the file `project.properties`

{% highlight bash %}
renderscript.opt.level=O0
{% endhighlight %} 

##Reference:       
1、[http://stackoverflow.com/questions/11255805/use-ant-clean-test-with-the-newest-android-sdk-renderscript-opt-level-is](http://stackoverflow.com/questions/11255805/use-ant-clean-test-with-the-newest-android-sdk-renderscript-opt-level-is)

