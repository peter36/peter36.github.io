---
layout: post
title: Use kdiff3 as Git diff tool 
categories: git cheatsheet blog
---

Git's difftool can be customized.  My favorite program is kdiff3 (which also runs on Windows), because it can do 3 way file comparison and is very useful during code merge.  Here are the steps to install and customize it for Git (on Ubuntu).

## 1. Install kdiff3

{% highlight bash %}
sudo apt-get install kdiff3
{% endhighlight %}

## 2. Change font for kdiff3

kdiff3 on Ubuntu has a bug that user cannot save preferencei from the GUI.  The font on Ubuntu is messed up, when you compare two files.  Sometimes the text and symbols may overlap.  To fix this, you need to edit the preference file manually:

{% highlight bash %}
 vi ~/.kde/share/config/kdiff3rc
{% endhighlight %}

The find the line "Font" and replace with 'Ubuntu Mono', like this:
{% highlight text %}
Font=Ubuntu Mono,9,-1,5,50,0,0,0,0,0
{% endhighlight %}

It should fix the font overlapping issue.

## 3. Configure Git difftool

Next, we configure Git to use kdiff3 as the diff tool.  Also, we disable the prompt which will ask you if you want to launch diff tool every time.

{% highlight bash %}
git config --global diff.tool=kdiff3
git config --global difftool.prompt=false
{% endhighlight %}

## 4. Try it

{% highlight bash %}
git difftool HEAD:hello.rb hello.rb
{% endhighlight %}

