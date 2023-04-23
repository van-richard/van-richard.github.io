---
layout: post
title: Git
description: 
---

## init
Create an empty Git repository. The Git repository’s settings, stored information, and more is stored in a directory (a folder) named `git`.

```
git init
```

## config 

To configure settings. Whether it be for the repository, the system itself, or global configurations ( global config file is ~/.gitconfig ).

```
$ git config --global user.email "MyEmail@Zoho.com"
$ git config --global user.name "My Name"

$ git config --global user.email
$ git config --global user.name
```

## add
To add files to the staging area/index. If you do not git add new files to the staging area/index, they will not be included in commits!

```
# add a file in your current working directory
$ git add HelloWorld.java

# add a file in a nested dir
$ git add /path/to/file/HelloWorld.c

# Regular Expression support!
$ git add ./*.java

# You can also add everything in your working directory to the staging area.
$ git add -A
```

## branch
Manage your branches. You can view, edit, create, delete branches using this command.

```
# list existing branches & remotes
$ git branch -a

# create a new branch
$ git branch myNewBranch

# delete a branch
$ git branch -d myBranch

# rename a branch
# git branch -m <oldname> <newname>
$ git branch -m myBranchName myNewBranchName

# edit a branch's description
$ git branch myBranchName --edit-description
```

## checkout
Updates all files in the working tree to match the version in the index, or specified tree.

```
# Checkout a repo - defaults to master branch
$ git checkout

# Checkout a specified branch
$ git checkout branchName

# Create a new branch & switch to it
# equivalent to "git branch <name>; git checkout <name>"

$ git checkout -b newBranch
```

## clone
Clones, or copies, an existing repository into a new directory. It also adds remote-tracking branches for each branch in the cloned repo, which allows you to push to a remote branch.

```
# Clone learnxinyminutes-docs
$ git clone https://github.com/adambard/learnxinyminutes-docs.git

# shallow clone - faster cloning that pulls only latest snapshot
$ git clone --depth 1 https://github.com/adambard/learnxinyminutes-docs.git

# clone only a specific branch
$ git clone -b master-cn https://github.com/adambard/learnxinyminutes-docs.git --single-branch
```

## commit
Stores the current contents of the index in a new “commit.” This commit contains the changes made and a message created by the user.

```
# commit with a message
$ git commit -m "Added multiplyNumbers() function to HelloWorld.c"

# signed commit with a message (user.signingkey must have been set
# with your GPG key e.g. git config --global user.signingkey 5173AAD5)
$ git commit -S -m "signed commit message"

# automatically stage modified or deleted files, except new files, and then commit
$ git commit -a -m "Modified foo.php and removed bar.php"

# change last commit (this deletes previous commit with a fresh commit)
$ git commit --amend -m "Correct message"
```

## pull
Pulls from a repository and merges it with another branch.

```
# Update your local repo, by merging in new changes
# from the remote "origin" and "master" branch.
# git pull <remote> <branch>
$ git pull origin master

# By default, git pull will update your current branch
# by merging in new changes from its remote-tracking branch
$ git pull

# Merge in changes from remote branch and rebase
# branch commits onto your local repo, like: "git fetch <remote> <branch>, git
# rebase <remote>/<branch>"
$ git pull origin master --rebase
```

## push
Push and merge changes from a branch to a remote & branch.

```
# Push and merge changes from a local repo to a
# remote named "origin" and "master" branch.
# git push <remote> <branch>
$ git push origin master

# By default, git push will push and merge changes from
# the current branch to its remote-tracking branch
$ git push

# To link up current local branch with a remote branch, add -u flag:
$ git push -u origin master
# Now, anytime you want to push from that same local branch, use shortcut:
$ git push
```