---
layout: post
title: Git Cheat Sheet (On Ubuntu) 
categories: git cheatsheet blog
---

Here are some quick tips for setting up or using Git on Linux (Ubuntu).

## Set Up A New Repository

## 1. Install Git For Linux

{% highlight bash %}
sudo apt-get install git
{% endhighlight %}

## 2. Configure GitHub

{% highlight bash %}
git config --global user.name "your_username"
git config --global user.email "your_email"
{% endhighlight %}

Replace the above "your_username" and "your_email" with your own user name and email address.

## 3. Create a local repository 

{% highlight bash %}
cd ~/projects
git init your_project
{% endhighlight %}

Replace the above "your_project" with your own project name (let's say 'hello') (prefer to be the same name as the repo on GitHub.  See the next step.)

## 4. Create repo on GitHub

Log on to http:://Github.com.  Click the "+" sign to add a new repo.

1. Enter a name for your repository.
2. Select either Public or Private.
3. Choose a license.

## 5. Create a README file

Back on your Ubuntu terminal, do:

{% highlight bash %}
vi README.md
git add README.md
{% endhighlight %}

## 6. Add files to the repository

{% highlight bash %}
vi hello.rb
git add hello.rb
{% endhighlight %}

The content of hello.rb is as follows:
{% highlight ruby %}
require 'sinatra'

get '/hello' do
  "Hello, how are you?"
end
{% endhighlight %}

## 7. Commit changes

{% highlight bash %}
git commit -am "your_checkin_comment"
{% endhighlight %}

Replace "your_checkin_comment" with your own comment.

## 8. Pull files from GitHub

Some times you might need to sync (merge) with the remote repo before you can push your update back to the repo.  In this case, we should pull the LICENSE file from the repo: 

{% highlight bash %}
git pull origin master
{% endhighlight %}

## 9. Push files to GitHub

Finally, you can push your update to the remote repo: 

{% highlight bash %}
git push origin master
{% endhighlight %}

# Clone (or branch) from another repository

## 1. Clone a remote repo

{% highlight bash %}
git clone https://github.com/your-username/your-repository.git
{% endhighlight %}


## 2. Create repo on GitHub

GO to http://github.com.  And create a new repo by clicking on the "+" sign.

## 3. Check your remote repository

{% highlight bash %}
git remote -v
{% endhighlight %}

## 3. Change remote origin

{% highlight bash %}
git remote set-url origin https://github.com/your-username/your-other-repository.git
{% endhighlight %}

## 4. Check if you are using your-other-repository

{% highlight bash %}
git remote -v
{% endhighlight %}

## 5. Ready to commit and push

Now your-other-repository is ready.

{% highlight bash %}
git commit -am "your-checkin-message"
git push origin master 
{% endhighlight %}



