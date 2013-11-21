---
layout: post
title: "How to install Heroku Toolbelt on CentOS 6.4"
description: "How to install Heroku Toolbelt on CentOS 6.4"
category: centos
tags: [centos, linux]
---
{% include JB/setup %}

1、install ruby
{% highlight bash %}
wget http://mirrors.ibiblio.org/ruby/1.9/ruby-1.9.2-p180.tar.gz tar -xvzf ruby-1.9.2-p180.tar.gz cd ruby-1.9.2-p180/ ./configure make && sudo make install 
{% endhighlight %}
<!-- more -->

2、install rubygems
{% highlight bash %}
wget http://rubyforge.org/frs/download.php/76728/rubygems-1.8.25.zip unzip rubygems-1.8.25.zip cd rubygems-1.8.25 ruby setup.rb 
{% endhighlight %}

3、install rb-readline
{% highlight bash %}
gem install rb-readline
{% endhighlight %}

4、install heroku toolbelt
{% highlight bash %}
wget -c https://toolbelt.herokuapp.com/install.sh && sh install.sh
{% endhighlight %}

Once installed, you will have access to the heroku command from your command shell. Log in using the email address and password you used when creating your Heroku account:

{% highlight bash %}
$ heroku login
Enter your Heroku credentials.
Email: adam@example.com
Password:
Could not find an existing public key.
Would you like to generate one? [Yn]
Generating new SSH public key.
Uploading ssh public key /Users/adam/.ssh/id_rsa.pub
{% endhighlight %}

You are now ready to create your first Heroku app:

{% highlight bash %}
$ cd ~/myapp
$ heroku create
Creating stark-fog-398... done, stack is cedar
http://stark-fog-398.herokuapp.com/ | git@heroku.com:stark-fog-398.git
Git remote heroku added
{% endhighlight %}

##Reference    
1、[https://gist.github.com/magic-hat/1080765](https://gist.github.com/magic-hat/1080765)            
2、[https://toolbelt.herokuapp.com/standalone](https://toolbelt.herokuapp.com/standalone)                         
3、[http://unix.stackexchange.com/questions/79390/locating-and-installing-a-program-heroku-toolbelt](http://unix.stackexchange.com/questions/79390/locating-and-installing-a-program-heroku-toolbelt)
