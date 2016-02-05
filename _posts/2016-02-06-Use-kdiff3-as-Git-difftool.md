---
layout: post
title: Use kdiff3 as Git diff tool 
categories: git cheatsheet blog
---

# Use kdiff3 as the diff tool 

Git's difftool can be customized.  I prefer to use kdiff3 (which also runs on Windows), because it can do 3 way file comparison.

## 1. Install kdiff3

{% highlight bash %}
sudo apt-get install kdiff3
{% endhighlighter %}

## 2. Change font for kdiff3

kdiff3 on Ubuntu has a bug that user cannot save preferencei from the GUI.  The font on Ubuntu is messed up, when you compare two files.  Sometimes the text and symbols may overlap.  To fix this, you need to edit the preference file manually:

{% highlight bash %}
 vi ~/.kde/share/config/kdiff3rc
{% endhighlighter %}

The find the line "Font" and replace with 'Ubuntu Mono', like this:
{% highlight text %}
Font=Ubuntu Mono,9,-1,5,50,0,0,0,0,0
{% endhighlighter %}

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

