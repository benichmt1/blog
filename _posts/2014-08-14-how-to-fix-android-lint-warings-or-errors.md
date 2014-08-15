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
 <br/> <br/>         
                      
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
 <br/> <br/>      
 
##3. The view name (@+id/phoneNum) suggests this is a phone number, but it does not include 'phone' in   the inputType           
**Solutions:**    
Just add this:        
{% highlight xml %}
android:inputType="phone"
{% endhighlight %}
 <br/> <br/>     
 
##4.The resource *** appears to be unused   
**Solutions:**    
Just delete it.     
 <br/> <br/>     
 
##5.Use a layout_width of 0dp instead of fill_parent for better performance
Just do it.     
 <br/> <br/>     
 
##6.Avoid passing null as the view root (needed to resolve layout parameters on the inflated layout's root element)
**Solutions:**    
Instead of doing

{% highlight java %}
convertView = infalInflater.inflate(R.layout.list_item, null);
{% endhighlight %}

do

{% highlight java %}
convertView = infalInflater.inflate(R.layout.list_item, parent, false);
{% endhighlight %}

It will inflate it with the given parent, but won't attach it to the parent.          

**Reference:**    
1. [http://stackoverflow.com/a/24832569](http://stackoverflow.com/a/24832569)       
 <br/> <br/>      
 
##7.To get local formatting use getDateInstance(), getDateTimeInstance(), or getTimeInstance(), or use new SimpleDateFormat(String template, Locale locale) with for example Locale.US for ASCII dates.
**Solutions:**    
To remove the warning just add Locale.getDefault() as the second argument while instantiating the date format object. Eg.        
{% highlight java %}
 SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss",
                    java.util.Locale.getDefault());
{% endhighlight %}

**Reference:**    
1. [http://stackoverflow.com/a/17808060](http://stackoverflow.com/a/17808060)       
 <br/> <br/> 
 
##8.This Handler class should be static or leaks might occur       
**Solutions:**    
I wrote that debugging code because of a couple of memory leaks I 
found in the Android codebase. Like you said, a Message has a 
reference to the Handler which, when it's inner and non-static, has a 
reference to the outer this (an Activity for instance.) If the Message 
lives in the queue for a long time, which happens fairly easily when 
posting a delayed message for instance, you keep a reference to the 
Activity and "leak" all the views and resources. It gets even worse 
when you obtain a Message and don't post it right away but keep it 
somewhere (for instance in a static structure) for later use. 

If you want to use the equivalent of an inner-class but not risk a 
leak, here's a simple pattern:     
{% highlight java %}
class OuterClass { 
  class InnerClass { 
    private final WeakReference<OuterClass> mTarget; 

    InnerClass(OuterClass target) { 
      mTarget = new WeakReference<OuterClass>(target); 
    } 

    void doSomething() { 
      OuterClass target = mTarget.get(); 
      if (target != null) target.do(); 

    } 
  } 
}      
{% endhighlight %}

For example:     
{% highlight java %}
static class IncomingHandler extends Handler {
    private final WeakReference<UDPListenerService> mService; 

    IncomingHandler(UDPListenerService service) {
        mService = new WeakReference<UDPListenerService>(service);
    }
    @Override
    public void handleMessage(Message msg)
    {
         UDPListenerService service = mService.get();
         if (service != null) {
              service.handleMessage(msg);
         }
    }
}
{% endhighlight %}

**Reference:**    
1. [http://stackoverflow.com/a/11408340](http://stackoverflow.com/a/11408340)             
2. [http://my.oschina.net/liucundong/blog/294127](http://my.oschina.net/liucundong/blog/294127)    
3. [http://www.androiddesignpatterns.com/2013/01/inner-class-handler-memory-leak.html](http://www.androiddesignpatterns.com/2013/01/inner-class-handler-memory-leak.html)       
4. [https://groups.google.com/forum/?fromgroups=#!msg/android-developers/1aPZXZG6kWk/lIYDavGYn5UJ](https://groups.google.com/forum/?fromgroups=#!msg/android-developers/1aPZXZG6kWk/lIYDavGYn5UJ)
             