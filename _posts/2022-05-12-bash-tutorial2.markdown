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

Quicklinks: [while](#while), [for](#for) 

# Background #

In this tutorial, we will go over the formating of loops, and then making these into scripts. Loops in bash (or any coding language in general) are those quality of life improvements you find as you tacking more daunting and reptetitive tasks. A bash loop is a statement that allows code to be repeatedly excuted. This allows us to take a series of commands and keep re-running them until a particular situation is reached.

There are loop structures in bash scripting, however, we'll look the 2 I use the most below.

# Loops #
One of the easiest and most useful loops to work with is `while`. When the while expression is true, keep executing these lines of code. The format of the command will look like this:

## while ##

{% highlight ruby %}
while [ arugment ]
do
[commands]
done
{% endhighlight %}

An example of using `while` loops can be if we want a sequence of numbers from 1 to 10. We'll start by setting a variable to a number. The variable I'll use is "value." The argument we'll use is when "value" is less than or equal (-le) to 10, print the number of "value", and then add 1 to value [((value++))]. Recall that the "$" is where I entered code, you'll see a new symbol (">") when excuting loops. Bash is essentially looking for you to end the loop with the statement "done."

{% highlight ruby %}
$ value=1
$ while [ $value -le 10 ]
>do
>echo $value
>((value++))
>done
{% endhighlight %}
 
The next loop structure I like to use is a `for` loop. This is a little different than `while`, namely, what it does is say for each item in a given list, perform the given set of commands. The `for` loop will take each item in the list (in that order), assign that item to the variable, and excute the commands between "do" and "done." The format looks like this:

## for ##

{% highlight ruby %}
for **variable** in [list]
do
[commands]
done
{% endhighlight %}

To illustrate this, here is an example of looping through a list of names:

{% highlight ruby %}
$ names='Richard Scott Van'
$ for name in $names
>do
>echo $name
>done
{% endhighlight %}



