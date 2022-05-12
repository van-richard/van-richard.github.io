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
> do
> echo $value
> ((value++))
> done
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
> do
> echo $name
> done
{% endhighlight %}

# Scripting #

I'm sure at this point, you're asking yourself when are you going to need this?? Say you wanted to use Alphafold to predict structures of your protein, but you have a lot of homologues. To keep things orderly, you might create separate folders for each homologue, and have the same inputs for each folder, where the only difference is the sequence. This will be a lot of copying, making files, and work. So we can use a loop, but what if you plan on doing this multiple times for other projects? We can save our commands to a bash script. Bash scripts are ordinary text files which contain commands or mixture of commands. An example could be what we did for the previous `for` loop. To turn it into a script, we'll add the ">" mark and give the file the name, "for loop example."

Now, how does bash differentiate between normal text files and scripts? We'll need to add a line to "for_loop_example.sh," specifically we'll add one line at the top. This line is called a Shebang which tells bash to read it as script. Additionally, I prefer to name my scripts with the ".sh" extension to differentiate this with other files. So the first thing I'll do is use `echo` to first make the Shebang, and then append (>>; two greater than symbols) the for loop to the file. 

{% highlight ruby %}
$ echo "$!/bin/bash" > for_loop_example.sh
$ names='richard scott van'
$ for name in $names
> do
> echo $name
> done >> for_loop_example.sh
{% endhighlight %}

If you `ls`, you should see the script. To run it, you'll type "bash" before the script:

{% highlight ruby %}
$ bash for_loop_example.sh
{% endhighlight %}

Once you get better, you can also use `vi` (or any text editor) to make a new file, and then write out the script manually.


