---
layout: post
title: "Command Line Tutorial! (Part 2)"
date: 2022-05-12 22:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  # Add image post (optional)
---
Welcome to part 2 of the Command Line Basic Usage!

In this tutorial, we'll go over the basics of loops, and making scripts. Loops in bash (or any coding language in general) are those quality of life improvements you'll find when it comes to daunting and repetitive task. A bash loop statement allows code to be repeatedly executed. This allow us to take a series of commands and keep re-running them until a particular situation is reached. 

There are 3 basic loop structures in Bash scripting which we'll look at below. 

# Table of Contents #

## PART 1 ##

**1A.** [Basic Usage Part 1](#basic-usage-part-1) (Navigating, Make Files) 

Quicklinks: [pwd](#pwd), [ls](#ls), [mkdir](#mkdir), [cd](#cd), [vim](#vim)

**1B.** [Basic Usage Part 2](#basic-usage-part-2) (Copy/Paste, Moving Files, Renaming, Misc.

Quicklinks: [cp](#cp), [mv](#mv), [rm](#rm)

## PART 2 ##

**2.** [Advanced Usage](#advanced-usage) (Scripting, loops, etc.)

**3.** [Other Usage](#other-usage) (Other quality of life improvemeents.)

# Background #

{% highlight ruby %}
$ echo $SHELL
{% endhighlight %}

This should return something like:

{% highlight ruby %}
/bin/bash
{% endhighlight %}

Personally, I use bash, and the following tutorial will be tailored towards that. If you would like to change your shell, run the following command in your Terminal.  

{% highlight ruby %}
$ chsh -s /bin/bash
{% endhighlight %}

# Basic Usage Part 1A #
Once again open your terminal (if you closed it), and you should see that you're logged into the command line environment with your account name and a dollar sign. The first command is `pwd`. `pwd` stands for Print Working Directory, which will tell you were you are currently located in your system. Two examples are shown, one is on my local macbook, and the other is on my supercomputing account.

