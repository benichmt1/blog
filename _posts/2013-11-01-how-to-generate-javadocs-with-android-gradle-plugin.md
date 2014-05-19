---
layout: post
title: "How To Generate JavaDocs with Android Gradle plugin"
description: "How To Generate JavaDocs with Android Gradle plugin"
category: android
tags: [android, gradle]
---
{% include JB/setup %}

When the Android Gradle Plugin is 0.10.0 or above. like "com.android.tools.build:gradle:0.10.0+"    
Add this task to your build.gradle

{% highlight java %}
    android.libraryVariants.all { variant ->

        task("generate${variant.name}Javadoc", type: Javadoc) {
            title = "$name $version API"
            description "Generates Javadoc for $variant.name."
            source = variant.javaCompile.source
            ext.androidJar =
                    "${android.sdkDirectory}/platforms/${android.compileSdkVersion}/android.jar"
            classpath = files(variant.javaCompile.classpath.files) + files(ext.androidJar)
            options.links("http://docs.oracle.com/javase/7/docs/api/");
            options.links("http://d.android.com/reference/");
            exclude '**/BuildConfig.java'
            exclude '**/R.java'
        }

    }
{% endhighlight %}

Then run the task.             
<!-- more -->

When the Android Gradle Plugin is 0.9.2 or below. like "com.android.tools.build:gradle:0.9.2"    
Add this task to your build.gradle

{% highlight java %}
    android.libraryVariants.all { variant ->

        task("generate${variant.name}Javadoc", type: Javadoc) {
            title = "$name $version API"
            description "Generates Javadoc for $variant.name."
            source = variant.javaCompile.source
            ext.androidJar =
                    "${android.plugin.sdkDirectory}/platforms/${android.compileSdkVersion}/android.jar"
            classpath = files(variant.javaCompile.classpath.files) + files(ext.androidJar)
            options.links("http://docs.oracle.com/javase/7/docs/api/");
            options.links("http://d.android.com/reference/");
            exclude '**/BuildConfig.java'
            exclude '**/R.java'
        }

    }
{% endhighlight %}

Then run the task.             

If you want to get more details,check the project as follows.      
[https://github.com/snowdream/android-gradle-template](https://github.com/snowdream/android-gradle-template)


  

Reference:                      
1、[http://stackoverflow.com/questions/17033878/generate-javadocs-with-android-gradle-plugin/19275671#19275671](http://stackoverflow.com/questions/17033878/generate-javadocs-with-android-gradle-plugin/19275671#19275671)

2、[http://www.gradle.org/docs/current/dsl/org.gradle.api.tasks.javadoc.Javadoc.html](http://www.gradle.org/docs/current/dsl/org.gradle.api.tasks.javadoc.Javadoc.html)

3、[http://stackoverflow.com/questions/15127624/excluding-buildconfig-class-and-r-class-from-android-library-jar-in-maven](http://stackoverflow.com/questions/15127624/excluding-buildconfig-class-and-r-class-from-android-library-jar-in-maven)

4、[http://svn.codehaus.org/gradle/gradle-core/tags/REL-0.5/build.gradle](http://svn.codehaus.org/gradle/gradle-core/tags/REL-0.5/build.gradle)

5、[http://hg.handverdrahtet.org/stp-addon/src/52a10770542fd3eef03ae31e6e555a03fb8a007d/build.gradle?at=default](http://hg.handverdrahtet.org/stp-addon/src/52a10770542fd3eef03ae31e6e555a03fb8a007d/build.gradle?at=default)

6、[https://github.com/fge/json-schema-core/blob/master/project.gradle](https://github.com/fge/json-schema-core/blob/master/project.gradle)

7、[http://code.ohloh.net/file?fid=wGYVgZm42hR6gjJiUx6-uvNos4s&cid=BJuUdFRczX4&s=&fp=1159&mp&projSelected=true#L0](http://code.ohloh.net/file?fid=wGYVgZm42hR6gjJiUx6-uvNos4s&cid=BJuUdFRczX4&s=&fp=1159&mp&projSelected=true#L0)

8、[https://bitbucket.org/controlsfx/controlsfx/src/5bae8b00d52e6d8c45ed34b7fe6d20bada8a1968/build.gradle?at=default](https://bitbucket.org/controlsfx/controlsfx/src/5bae8b00d52e6d8c45ed34b7fe6d20bada8a1968/build.gradle?at=default)

9、[http://stackoverflow.com/questions/23604147/getting-android-sdk-dir-with-android-gradle-tools-1-10](http://stackoverflow.com/questions/23604147/getting-android-sdk-dir-with-android-gradle-tools-1-10)         

10、[https://plus.google.com/+GabrieleMariotti/posts/NphSRvqAo6m](https://plus.google.com/+GabrieleMariotti/posts/NphSRvqAo6m)         

