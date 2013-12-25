---
layout: post
title: "How to develop with android gradle template"
description: "How to develop with android gradle template"
category: android
tags: [github, android, gradle]
---
{% include JB/setup %}

android-gradle-template is a template for android with gradle.How to develop with it?

###1、Installing Android Studio
Android Studio is a new Android development environment based on IntelliJ IDEA. Similar to Eclipse with the ADT Plugin, Android Studio provides integrated Android developer tools for development and debugging.
Download the lastest from [http://tools.android.com/download/studio/canary/0-4-0](http://tools.android.com/download/studio/canary/0-4-0)                            
Install it as follows:                            
[http://developer.android.com/sdk/installing/studio.html#Installing](http://developer.android.com/sdk/installing/studio.html#Installing)                            
<!-- more -->

###2、Installing Gradle 1.9
Gradle is build automation evolved. Gradle can automate the building, testing, publishing, deployment and more of software packages or other types of projects such as generated static websites, generated documentation or indeed anything else.                            
Install it as follows:                             
[http://www.gradle.org/docs/1.9/userguide/installation.html](http://www.gradle.org/docs/1.9/userguide/installation.html)                            


###3、Clone the repo
{% highlight xml %}
    git clone git@github.com:snowdream/android-gradle-template.git
{% endhighlight %}

###4、Create and modify the file gradle.properties
create a file with the name  gradle.properties in the directory "$USE_HOME/.gradle/"
copy the following content to gradle.properties and modify it .                
[https://gist.github.com/snowdream/8120098](https://gist.github.com/snowdream/8120098)

* "signing." is your gpg configuration.
* "android.signingConfigs.release." is your release keystore configuration.
* "nexusUsername and nexusPassword" is you username and password in the website oss.sonatype.org.
* "POM_LICENCE" is your default license configuration.
* "POM_DEVELOPER" is the default developer configuration.

Then you can modify the gradle.propertie located in project build dir as you need.

That'is it,Enjoy it.

