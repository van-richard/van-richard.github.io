---
layout: post
title: "Command Line Tutorial! (Part 1)"
date: 2022-03-30 22:00:00 +0000
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img:  # Add image post (optional)
---
Are you ready? Because, I'm about to change your world!!!! 

This post is dedicated to developing your skills in usage of the command line interface. Like any programming language, it will be overwhelming at first and will take a little practice and getting use to. My goal for this tutorial is for you to be comfortable with basic syntax, and eventually develop your own scripts to start automating your tasks (no one likes repetitive tasks, right?). To do that, I will break the tutorial into 3 sections. In the first section, Basic Usage, you will learn how to navigate around the Terminal/Linux command line with Bash (more info on this later~). The second section, Advanced Usage, will cover scripting, loops, and other "advanced" features (Quotes on advanced because I don't like differentiating between basic and advanced uses, but for the tutorial's sake *sigh*). The last section, Other Uses, will cover other command line functions that I found useful from scripting for Molecular Dynamics simulations and Bio/Chem-informatics.    

Feel free to refer back to this page as you go on. 

# Table of Contents #

## PART 1 ##

**1A.** [Basic Usage Part 1](#basic-usage-part-1) (Navigating, Make Files) 

Quicklinks: [pwd](#pwd), [ls](#ls), [mkdir](#mkdir), [cd](#cd), [vim](#vim)

**1B.** [Basic Usage Part 2](#basic-usage-part-2) (Copy/Paste, Moving Files, Renaming, Misc.

Quicklinks: [cp](#cp), [mv](#mv), [rm](#rm)

## PART 2 ##

**2.** [Advanced Usage](/_posts/2022-05-12-bash-tutorial.markdown) (Scripting, loops, etc.)

**3.** [Other Usage](#other-usage) (Other quality of life improvemeents.)

# Background #
NOTE 1: Example code will be shown in cells, where the "$" (dollar sign) represents the input command. Cells without the "$" (dollar sign) will represent output of said command. This is because the command shell will tell you what type of user you are when you're logged into the command line environment. The dollar sign represents normal user.

NOTE 2: When coding, naming files/folders should be descriptive. This often requires us to use multiple words separated by a space such as: blue sky, red ball, etc. While naming files/folders can include spaces, we often separate them by dashes (-) or underscores (__). This is because names containing spaces require quotes when calling them through commmand line. In this tutorial, I will use underscores (__).

Briefly, the command shell is just a program that takes in text commands, passes this information to your computer, and runs them. There are a few different flavors of command shells, such as bash, csh, ksh, DOS (Windows), etc. Although there are some overlap between the languages, each may contain their own special syntax for specific functions. If you're ever in doubt, you can find which flavor you're using by running the following command on your Terminal. Then Google your shell name + "cheat sheet" (Ex: "bash cheat sheet"), and look at images. 

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

Going back into the "test_1" folder, we are now going make a file. While there are a few ways to make files, I want to start with the harder method first (Not necessarily difficult, but takes a lot of getting use to). I will only cover the basics of Vim, while leaving the more fun stuff in [Other Uses](#other-uses).

We will use a text editor called Vim, which you could say is similar with Notepad, etc. The command to run Vim is `vi` following with the file name and file data type. We will make a text file called "test."

## vim ## 
vim - text editor (makes, edits files).

{% highlight ruby %}  
$ vi test.txt
{% endhighlight %}

This should take you to an empty page. To start editing the file, we will press the `i` key. Notice that the lower left hand corner of your screen shows that you are now in editing mode. 

Type "Hello World!" into the editor.

Once written, save the file by pressing the `esc` key, and typing `:wq`. The `esc` key will allow you to exit editing mode, which should change the lower left hand corner of the screen again. `:wq` tells vim to save (`w` - write) and quit (`q`). More functions of Vim will be shown in [Other Uses](#other-uses). 

Now you have a new file called "text.txt" in your folder "test_1".

# Basic Usage Part 1B #

At this point, we can start learning how to copy/paste, move, and  rename files/folders!

To copy files, we will use the `cp` command. The format of the operation follows:

{% highlight ruby %}
$ cp FILE1 FILE2 
{% endhighlight %}

It's also important to know that you don't have to be in your working directory. FILE1 and FILE2 can point to the location you want to copy. Say that you want to copy the file back one folder it would look like:

{% highlight ruby %}
$ cp FILE1 ../FILE2 
{% endhighlight %}

## cp ##

{% highlight ruby %}
$ cp test.txt test2.txt
{% endhighlight %}

You should see that you have two text file copies. If you use `cat` on both files, they should contain the same information.

To copy a folder we need to add a flag with to the copy command, like `cp -r`. Flags allow you to modify the operation of the command, in the case of `cp -r`, we want to "**c**o**p**y folde**r**". In this example, we will copy the folder test_1. To do so, we'll need to change directories out one folder.

{% highlight ruby %}
$ cd ..
$ cp -r test_1 test_2
{% endhighlight %}

The next command is `mv`, which can both move folders and rename! To move a folder, you will specify the folder you want to move, and then the location you want to move the file/folder too. Unlike `cp` which requires the `-r` flag to specify folder, `mv` will work on both files/folders. As an example, we'll make a new folder called "new_directory", and move test_2 to it.

{% highlight ruby %}
$ mv FOLDER1 FOLDER2
{% endhighlight %}

## mv ##

{% highlight ruby %}
$ mkdir new_directory
$ mv test_2 new_directory
{% endhighlight %}

If you `ls` your current directory, you should see that test_2 is no longer there, and that a new folder is made. If you `cd` into "new_directory", you should see that test_2 is there, along with the contents of the folder (test2.txt).

Now as a recep, we've learned to navigate our computer via the command line with `cd`, look at and make files `vi`, copy `cp`, and move/rename files/folders `mv`. The last commmand for this short introduction is deleting files/folders. Similar to copying, if we want to remove a folder, we'll need to add a "-r" flag. First, we will delete a file in the "new_directory folder." Then we'll delete the "test_1" folder.

{% highlight ruby %}
$ rm FILENAME
{% endhighlight %}

or 

{% highlight ruby %}
$ rm -r FOLDERNAME
{% endhighlight %}

## rm ##

{% highlight ruby %}
$ cd new_directory
$ rm test2.txt
$ ls
$ cd ..
$ rm -r test_1
{% endhighlight %}

This conclude the introduction and basic usage of command line! There are tons of other commands that can be learned to help you achieve whatever goal you need, but everything I've shown you today should get you started with command line. Thank you for following!

If you're interested in more advanced usage, you can move on to Part 2 of the tutorial! 


