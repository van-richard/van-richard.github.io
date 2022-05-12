---
layout: post
title: "Command Line Tutorial! (Part 2)"
date: 2022-05-12
description: 
img:
---

Welcome to part 2 of the Command Line basic Usage tutorials!!

# Table of Contents #
**2.** Advanced Usage (loops, scripting, etc.)

Quicklinks: 

# Background #

In this tutorial, we will go over the formating of loops, and then making these into scripts. Loops in bash (or any coding language in general) are those quality of life improvements you find as you tacking more daunting and reptetitive tasks. A bash loop is a statement that allows code to be repeatedly excuted. This allows us to take a series of commands and keep re-running them until a particular situation is reached.

There are 3 basic loop structures in bash scripting which we'll look at below.

# Loops #
One of the easiest and most useful loops to work with is `while`. When the while expression is true, keep executing these lines of code. The format of the command will look like this:

## while ##

{% highlight ruby %}
while [arugment]
do
[commands]
done
{% endhighlight %}

An example of using `while` loops can be if we want a sequence of numbers from 1 to 10. We'll start by setting a variable to a number. The variable I'll use is "value." The argument we'll use is when "value" is less than or equal (-le) to 10, print the number of "value", and then add 1 to value [((value++))] :

{% highlight ruby %}
$ value=1
$ while [ $value -le 10 ]
do
echo $value
((value++))
done
{% endhighlight %}
 
