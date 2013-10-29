---
layout: post
title: "Git auto completion for the bash shell"
description: "Git auto completion for the bash shell"
category: git
tags: [git]
---
{% include JB/setup %}

You can enable auto-completion for Git commands in the bash shell. For this copy the following file to your home directory under the name “.git-completion.bash”.

[https://raw.github.com/git/git/master/contrib/completion/git-completion.bash](https://raw.github.com/git/git/master/contrib/completion/git-completion.bash)

Afterwards add the following lines to your .bashrc file and restart the bash.
{% highlight bash %}

if [ -f ~/.git-completion.bash ]; then
. ~/.git-completion.bash
fi

{% endhighlight %}

Now you have code completion, e.g. if you type git c and press tag you see the possible values.

