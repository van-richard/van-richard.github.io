---
layout: post
title: SSH to Remote Server 
description: Tips and Tricks for Remote Access to the Supercomputer
---


Examples shown below references the OSCER Supercomputer at the University of Oklahoma. However, this similar commands can be used for other supercomputers with minor adjustments.

If your OS is Linux/Mac, please skip to: [Login](slurm.html)

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


 
