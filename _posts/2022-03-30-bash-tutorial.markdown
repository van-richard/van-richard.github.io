---
layout: post
title: "Command Line Tutorial!"
date: 2022-03-30 22:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  # Add image post (optional)
---
Are you ready? Because, I'm about to change your world!!!! 

This post is dedicated to developing your skills in usage of the command line interface. Like any programming language, it will be overwhelming at first and will take a little practice and getting use to. My goal for this tutorial is for you to be comfortable with basic syntax, and eventually develop your own scripts to start automating your tasks (no one likes repetitive tasks, right?). To do that, I will break the tutorial into 3 sections. In the first section, Basic Usage, you will learn how to navigate around the Terminal/Linux command line with Bash (more info on this later~). The second section, Advanced Usage, will cover scripting, loops, and other "advanced" features (Quotes on advanced because I don't like differentiating between basic and advanced uses, but for the tutorial's sake *sigh*). The last section, Other Uses, will cover other command line functions that I found useful from scripting for Molecular Dynamics simulations and Bio/Chem-informatics.    

Feel free to refer back to this page as you go on. 

# Table of Contents #
[Basic Usage](#basic-usage) 

[Advanced Usage](#advanced-usage)

[Other Usage](#other-usage)

# Background #
NOTE: Example code will be shown in cells, where the "$" (dollar sign) represents the input command. Cells without the "$" (dollar sign) will represent output of said command. This is because the command shell will tell you what type of user you are when you're logged into the command line environment. The dollar sign represents normal user.

Briefly, the command shell is just a program that takes in text commands, passes this information to your computer, and runs them. There are a few different flavors of command shells, such as bash, csh, ksh, DOS (Windows), etc. Although there are some overlap between the languages, each may contain their own special syntax for specific functions. If you're ever in doubt, you can find which flavor you're using by running the following command on your Terminal. Then Google your shell name + "cheat sheet" (Ex: "bash cheat sheet"), and looking at images. 

{% highlight ruby %}
$ echo $SHELL
{% end highlight %}

This should return something like:

{% highlight ruby %}
/bin/bash
{% end highlight %}

Personally, I use bash, and the following tutorial will be tailored towards that. If you would like to change your shell, run the following command in your Terminal.  

{% highlight ruby %}
$ chsh -s /bin/bash
{% end highlight %}

# Basic Usage #
## pwd ## 
Once again open your terminal (if you closed it), and you should see that you're logged into the command line environment with your account name and a dollar sign. The first command is 'pwd'  

# Advanced Usage #

# Other Usage #


