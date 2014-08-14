---
layout: post
title: "how to fix android lint warings or errors "
description: "how to fix android lint warings or errors"
category: android 
tags: [android]
---
{% include JB/setup %}

##1. [Accessibility] Missing contentDescription attribute on image           
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