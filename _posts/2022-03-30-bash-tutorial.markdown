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
{% endhighlight %}

This should return something like:

{% highlight ruby %}
/bin/bash
{% endhighlight %}

Personally, I use bash, and the following tutorial will be tailored towards that. If you would like to change your shell, run the following command in your Terminal.  

{% highlight ruby %}
$ chsh -s /bin/bash
{% endhighlight %}

# Basic Usage #
Once again open your terminal (if you closed it), and you should see that you're logged into the command line environment with your account name and a dollar sign. The first command is `pwd`. `pwd` stands for Print Working Directory, which will tell you were you are currently located in your system. Two examples are shown, one is on my local macbook, and the other is on my supercomputing account.

NOTE: Typically, your shell will always start at your default home location (if this is a new window that is opened for your terminal). Your home is usually set when you first made an account, and should have access to folders such as, Desktop, Documents, Pictures, etc.

## pwd ## 
pwd (print working directory) - outputs (prints) the location of your current working directory.

{% highlight ruby %}  
$ pwd 
{% endhighlight %}

{% highlight ruby %}  
/Users/van 
{% endhighlight %}

{% highlight ruby %}  
/home/van/ 
{% endhighlight %}


Question: What do you do if you need to find your homework file on your computer? Usually, I would have the file saved to some course folder, and I would have to navigate the Finder app to get to Documents, and then course folder. To do the same thing in terminal, you'll need to run a command called `ls`. This command will list all files and folders in your current directory (You will use this command all the time!). Because this command will vary depending on the user, I will not have an example output, but you should see folders represented by blue text, and files represented by white text. 
 
## ls ## 
ls (list) - lists file/folders in current directory.

{% highlight ruby %}  
$ ls 
{% endhighlight %}

Let's make a new folder called "test_1" for us to work in. The command will be `mkdir` which stands for make directory. What follows the command will the folder's name. This command is the same as right-clicking on your Desktop, and creating a new folder. Please be aware that folder names cannot have spaces. For example, if we wanted to name our folder, "test 1", the `mkdir` command will recognize this as making two folders, one "test", and the second "1." Because of this, you often see most files/folders with a "-" (hyphen) or "_" (underscore). 

If you run the `ls` command, you'll see your new folder "test_1."

## mkdir ## 
mkdir (make directory) - makes a new folder. 

{% highlight ruby %}  
$ mkdir test_1
{% endhighlight %}

To go into a folder, we will run the command `cd`. `cd` stands for change directory. This is the same as double clicking a folder on your Desktop, or file to open. Once you hit enter, you should see that the dollar sign reset, and you're able to run your next command.

To check whether or not we are in the folder, run `pwd`. The new output should look like mine with the exception of the username.

## cd ## 
cd (change directory) - allows you to enter a directory (folder).

{% highlight ruby %}  
$ cd test_1
$ pwd
{% endhighlight %}

{% highlight ruby %}  
/Users/van/test_1
{% endhighlight %}

To go out a folder, we will still use `cd`, but rather than typing a folder name, we will use two periods. 

Again, type `pwd` to check whether or not you left the "test_1" folder. Your output from `pwd` should again be like our first example of the command.

{% highlight ruby %}  
$ cd ..
$ pwd
{% endhighlight %}

Going back into the "test_1" folder, we are now going make a file. While there are a few ways to make files, I want to start with the harder method first (Not neccessarily difficult, but takes a lot of getting use to). I will only cover the basics of Vim, while leaving the more fun stuff in [Other Uses].

We will use a text editor called Vim, which you could say is similar with Notepad, etc. The command to run Vim is `vi` following with the file name and file data type. We will make a text file called "test."

## vim ## 
vim - text editor (makes, edits files).

{% highlight ruby %}  
$ vi test.txt
{% endhighlight %}

This should take you to an empty page. To start editing the file, we will press the `i` key. Notice that the lower left hand corner of your screen shows that you are now in editing mode. 

Type "Hello World!" into the editor.


# Advanced Usage #

# Other Usage #
