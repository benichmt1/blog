---
layout: post
title: "how to fix android lint warings or errors "
description: "how to fix android lint warings or errors"
category: android 
tags: [android]
---
{% include JB/setup %}

##1.  [Accessibility] Missing contentDescription attribute on image           
**Solutions 1:**         
Just add this:        
{% highlight xml %}
android:contentDescription="@string/description"
{% endhighlight %}

then go to yours Strings.xml and add this:

{% highlight xml %}
<string name="description"> YOUR_DESCRIPTION_HERE </string>
{% endhighlight %}

as of your code:

{% highlight xml %}
<ImageButton
    android:id="@+id/callbannerbuttonpg1"
    android:layout_width="fill_parent"
    android:layout_height="wrap_content"
    android:layout_marginTop="157dp"
    android:background="@null"
    android:src="@drawable/callbanner"
    android:visibility="invisible"
    android:contentDescription="@string/description" /> 
 {% endhighlight %}
<!-- more -->  

**Solutions 2:**    
Just add this:        
{% highlight xml %}
android:contentDescription="@null"
{% endhighlight %}

**Description:**       
It's for accessibility for the blind. For accessibility, apps that utilize the contentDescription help blind people navigate by using Android's text-to-speech capabilities.          
So if someone selects an ImageButton via a trackpad or something, the TTS can speak the contentDescription so they can easily navigate the app. See [this](http://developer.android.com/guide/practices/design/accessibility.html#LabelInputs) for more information.          
    
**Reference:**    
1. [http://stackoverflow.com/a/24723362](http://stackoverflow.com/a/24723362)          
2. [http://stackoverflow.com/a/24399293](http://stackoverflow.com/a/24399293)           
3. [http://stackoverflow.com/a/9197792](http://stackoverflow.com/a/9197792)         


##2. [I18N] Hardcoded string "检测结果", should use @string resource
**Solutions:**      
It is not good practice to hard code strings into your layout files. You should add them to a string resource file and then reference them from your layout.

This allows you to update every occurrence of the word "Yellow" in all layouts at the same time by just editing your strings.xml file.

It is also extremely useful for supporting multiple languages as a separate strings.xml file can be used for each supported language.

example: XML file saved at res/values/strings.xml:   
{% highlight xml %}  
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="yellow">Yellow</string>
</resources>
{% endhighlight %}   

This layout XML applies a string to a View:

{% highlight xml %}  
<TextView android:layout_width="fill_parent"
          android:layout_height="wrap_content"
          android:text="@string/yellow" />
{% endhighlight %}   

Similarly colors should be stored in colors.xml and then referenced by using @color/color_name

{% highlight xml %}  
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="Black">#000000</color>
</resources>
{% endhighlight %}   

    
**Reference:**    
1. [http://stackoverflow.com/a/8743887](http://stackoverflow.com/a/8743887)         