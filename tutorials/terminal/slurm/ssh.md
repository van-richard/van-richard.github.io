---
layout: post
title: SSH to Remote Server 
description: Tips and Tricks for Remote Access to the Supercomputer
---


Examples shown below references the OSCER Supercomputer at the University of Oklahoma. However, this similar commands can be used for other supercomputers with minor adjustments.


## Linux/Mac

If your OS is Linux/Mac, login is straight forward (`<username>` is your username): 

```
ssh <username>@schooner.oscer.ou.edu 
```
<br />

### Login with no password

On your computer, run the following:

```
ssh-keygen -t rsa -b 4096
```
<br />

**NOTE:** Do not set a passphrase when creating the key (Press enter 3 times). Make sure that this file is only readable by you! The public key file (id_dsa.pub or id_rsa.pub) as the name implies can be uploaded to other systems to which you would like passwordless access.

Now, create a `~/.ssh` directory on the cluster (doesn't matter if this is already there).

```
ssh <username>@schooner.oscer.ou.edu mkdir -p .ssh
```
<br />

Append the public key to the cluser and enter password one last time:

```
cat .ssh/id_rsa.pub | ssh <username>@schooner.oscer.ou.edu `cat >> ~/.ssh/authorized_keys`
```
<br />

## Windows

If your OS is Windows and you need to SSH to a remote server, you have 2 options:

1. SSH with Windows Powershell (**REQ:** Windows 10, Powershell 5.1+, Adminstrative Access).
2. SSH with PuTTy.

### SSH with Windows Powershell ###

**Prerequsite Checklist**

Open Powershell and Run as Administrator.

Run winver.exe and press enter to see the version details for your Windows device.

```
$ winver.exe
```
<br />
Run $PSVersionTable.PSVersion. Verify your major version is at least 5, and your minor version at least 1. Learn more about installing PowerShell on Windows.

```
$ PSVersionTable.PSVersion
```
<br />
Run the command below. The output will show True when you're a member of the built-in Administrators group.

```
$ (New-Object Security.Principal.WindowsPrincipal([Security.Principal.WindowsIdentity]::GetCurrent())).IsInRole([Security.Principal.WindowsBuiltInRole]::Administrator)
```
<br /> 
