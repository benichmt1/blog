---
layout: post
title: "How to rename the apk with gralde"
description: "How to rename the apk with gralde"
category: android
tags: [android, gradle]
---
{% include JB/setup %}

Modify and add the following script to the "buildTypes".
The "POM_NAME" is my custom project name,such as "android-downloader" 
{% highlight java %}
        applicationVariants.all { variant ->
            def apk = variant.packageApplication.outputFile;
            def newName = "";

            newName = apk.name.replace(project.name,POM_NAME + "-v" + defaultConfig.versionName);
            newName = newName.replace("-" + variant.buildType.name, "");
            newName = newName.replace(".apk", "-" + variant.buildType.name.toLowerCase() + ".apk");

            variant.packageApplication.outputFile = new File(apk.parentFile, newName);
            if (variant.zipAlign) {
                variant.zipAlign.outputFile = new File(apk.parentFile, newName.replace("-unaligned", ""));
            }
        }
{% endhighlight %}
<!-- more -->


Reference:       
1、[https://groups.google.com/d/msg/adt-dev/4_-5NvxuFB0/Epc20PsMrZsJ](https://groups.google.com/d/msg/adt-dev/4_-5NvxuFB0/Epc20PsMrZsJ)     
2、[http://stackoverflow.com/questions/18507660/renaming-apk-with-gradle-getting-same-apk-twice](http://stackoverflow.com/questions/18507660/renaming-apk-with-gradle-getting-same-apk-twice)                  
3、[https://groups.google.com/forum/#!topic/adt-dev/RIwlpnioB2M](https://groups.google.com/forum/#!topic/adt-dev/RIwlpnioB2M)                     
4、[http://androiddev.orkitra.com/?p=77889](http://androiddev.orkitra.com/?p=77889)                               


