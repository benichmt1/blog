---
layout: post
title: "Building with AndroidAnnotations and Gradle"
description: "Building with AndroidAnnotations and Gradle"
category: android
tags: [android, gradle]
---
{% include JB/setup %}

This is similar to robotoaster's response, but it works in 0.4.1 and it places the generated java source files in a new directory (consistent with the other generated source folders), which allows Android Studio to see the source and stop complaining. It also works with more annotation processors. Just add your annotation processors to the "apt" configuration.
<!-- more -->


{% highlight groovy  %}
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:0.4.1'
    }
}
apply plugin: 'android'

repositories {
    mavenCentral()
}

ext.daggerVersion = '1.0.0';
ext.androidAnnotationsVersion = '2.7.1';

configurations {
    apt
}

dependencies {
    apt "com.googlecode.androidannotations:androidannotations:${androidAnnotationsVersion}"
    compile "com.googlecode.androidannotations:androidannotations-api:${androidAnnotationsVersion}"
    apt "com.squareup.dagger:dagger-compiler:${daggerVersion}"
    compile "com.squareup.dagger:dagger:${daggerVersion}"
}

android {
    compileSdkVersion 17
    buildToolsVersion "17.0.0"

    defaultConfig {
        minSdkVersion 10
        targetSdkVersion 17
    }
}

android.applicationVariants.all { variant ->
    aptOutput = file("${project.buildDir}/source/apt_generated/${variant.dirName}")
    println "****************************"
    println "variant: ${variant.name}"
    println "manifest:  ${variant.processResources.manifestFile}"
    println "aptOutput:  ${aptOutput}"
    println "****************************"

    variant.javaCompile.doFirst {
        println "*** compile doFirst ${variant.name}"
        aptOutput.mkdirs()
        variant.javaCompile.options.compilerArgs += [
                '-processorpath', configurations.apt.getAsPath(),
                '-AandroidManifestFile=' + variant.processResources.manifestFile,
                '-s', aptOutput
        ]
    }
}
{% endhighlight %}

**UPDATE**: This still works to compile, but with Android Studio 0.1.1 you can no longer edit your project structure with the UI, so you can't tell AS to look at the new source folder. I'd like to add the folder to a sourceSet, but variants don't seem to actually have their own sourceSets so I'm not sure yet where to put it.

**UPDATE 2**: You can get Android Studio 0.1.1 to recognize the apt-generated source files by right-clicking on build/source/apt_generated/debug in the project browser and selecting Mark Directory As->Source Root

**UPDATE 3**: Since gradle plugin 0.5.5 the android.applicationVariants.each does not work anymore. Use android.applicationVariants.all instead. See the changelog at android.com: access to the variants container don't force creating the task. This means android.[application|Library|Test]Variants will be empty during the evaluation phase. To use it, use .all instead of .each



**Attention**           
Also if your gradle build file uses the packageNameSuffix attribute, you need to add the parameter **-AresourcePackageName=yourPackage** or your R class wont be find by the AA processor (need latest AA 3.0) –  tbruyelle Jun 28 at 11:35










From: [androidannotations-nothing-generated-empty-activity][1]
[1]:http://stackoverflow.com/questions/16683944/androidannotations-nothing-generated-empty-activity


