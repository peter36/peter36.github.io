---
layout: post
title: Git Cheat Sheet (On Ubuntu) 
categories: git cheatsheet blog
---

# Set Up A New Repository

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

## 8. Pull files from GitHub

## 9. Push files to GitHub

# Clone (or branch) from another repository

## 1. Clone a remote repo

## 2. Create repo on GitHub

## 3. Modify file 

## 4. Commit changes

## 5. Change remote origin

## 6. Push files to your own repo


