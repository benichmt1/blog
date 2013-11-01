---
layout: post
title: "How To Generate JavaDocs with Android Gradle plugin"
description: "How To Generate JavaDocs with Android Gradle plugin"
category: android
tags: [android, gradle]
---
{% include JB/setup %}

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
            exclude '**/BuildConfig.java'
            exclude '**/R.java'
        }

    }
{% endhighlight %}

Then run the task.
<!-- more -->

Reference:                      
1、[http://stackoverflow.com/questions/17033878/generate-javadocs-with-android-gradle-plugin/19275671#19275671](http://stackoverflow.com/questions/17033878/generate-javadocs-with-android-gradle-plugin/19275671#19275671)

2、[http://www.gradle.org/docs/current/dsl/org.gradle.api.tasks.javadoc.Javadoc.html](http://www.gradle.org/docs/current/dsl/org.gradle.api.tasks.javadoc.Javadoc.html)

3、[http://stackoverflow.com/questions/15127624/excluding-buildconfig-class-and-r-class-from-android-library-jar-in-maven](http://stackoverflow.com/questions/15127624/excluding-buildconfig-class-and-r-class-from-android-library-jar-in-maven)

4、[http://svn.codehaus.org/gradle/gradle-core/tags/REL-0.5/build.gradle](http://svn.codehaus.org/gradle/gradle-core/tags/REL-0.5/build.gradle)

