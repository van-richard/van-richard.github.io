---
layout: post
title: Quickstart to SLURM Commands
description: Commands to assist in navigating SLURM environments
---

Examples shown below references the OSCER Supercomputer at the University of Oklahoma. However, this similar commands can be used for other supercomputers with minor adjustments.

NOTE: Change `<username>` with your supercomputing account name.

## Table of Content

1. [Login](#Login)
2. [Submitting Jobs](#Submitting-Jobs)
3. [SLURM Queue](#checking-slurm-queue)
4. [Node Information](#get-node-information)
5. [Download Files/Folders](#download-filesfolders)
6. [Upload Files/Folders](#uploading-filesfolders)

## Login 

OSCER has 2 login nodes, if you don't specify which of the two, then it will automatically chose on for you.

```
ssh <username>@schooner.oscer.ou.edu    # Auto
```
```
ssh <username>@schooner1.oscer.ou.edu   # Login Node 1
```
```
ssh <username>@schooner2.oscer.ou.edu   # Login Node 2
```  
<br />

## Submitting Jobs

To submit jobs to the SLURM scheduler, use `sbatch` followed by the name of your batch script.

```
sbatch script.slurm
```
<br />

### SLURM flags

| Option                  | Meaning |
| :-----                  | :------ |
| \--partition=NAME       | Job to run on partition "NAME" |
| \--time=HH:MM:SS        | Amount of wall time requested for job (Hours:Minutes:Seconds) | 
| \--nodes=#              | Number of nodes to use |
| \--ntasks=#             | Number of tasks (processors) to be run |
| \--cpus\-per\-task=#    | Number of CPUs required for each task (e.g. '8' for an 8-way multithreaded job) |
| \--ntasks\-per\-core=1  | Do not use hyperthreading (this flag typically used for parallel jobs) | 
| \--mem=#g               | Memory required for the job (Note the g (GB) in this option) |
| \--exclusive            | Allocate the node exclusively |
| \--error=%j.err         | JOBID as name of stderr file (by default, slurm######.out in the submitting directory) | 
| \--output=%j.out        | JOBID as name of stdout file (by default, slurm######.out in the submitting directory) | 
| \--job\-name=NAME       | Name your job, "NAME", so you can identify it in the queue |
| \--array=0-#            | Mechanism for submitting and managing similar jobs (# can be index values) |

### Example

Example of debug batch script.

```
#!/bin/bash
#SBATCH --partition=debug
#SBATCH --nodes=1
#SBATCH --ntasks=1
#SBATCH --mem=1g
#SBATCH --output=%j.out
#SBATCH --error=%j.err
#SBATCH --time=00:05:00
#SBATCH --job-name=example
```
<br />

## Checking SLURM queue 

Shows all jobs running/pending in queue.

```
squeue 
```
<br />
Show *your* jobs that are running/pending in queue.

```
squeue -u <username> 
```
<br />
Find running/pending jobs for a specific partition.

```
squeue -p <ParitionName>
```
<br />

## Get Node information

List nodes.

```
sinfo
```
<br />
Find all available nodes.

```
sinfo | grep "idle"
```
<br />
Find information on why a specific node is down

```
sinfo -R
```
<br />

## Download Files/Folders

There are 2 options to downloading files and folders.

1. Download with `scp` (Good for small and/or few files/folders) 
    - For files, you will need to be in a second terminal where the _working directory is on your local computer_ and where you want the file to be located
    - For Folders, follow the previous step, and add the flag `scp -r`.
2. Download with `rsync` (For copying large amounts of data, and generally the preferred approach).
    - If a lot of data needs to be transfered it is also preferred to use the data transfer login node on OSCER (dtn2.oscer.ou.edu).
    - Same approach as `scp` but use the flags `rsync -avuim`.
    - `-a` archive - preserve as most of the data.
    - `-v` verbose - print summary of file transfer.
    - `-u` update - only newest file will be kept.
    - `-i` itemize - list of the changes.
    - `-m` prune - delete empty folders.

```
scp <username>@schooner.oscer.ou.edu:/path/to/file .               # File Download
```
```
scp <username>@schooner.oscer.ou.edu:/path/to/directory .          # Folder Download
```
<br />
```
rsync -avuim <username>@dtn2.oscer.ou.edu:/path/to/file .      # File Download
```
```
rsync -avuim <username>@dtn2.oscer.ou.edu:/path/to/directory . # Folder Download
```
<br />

## Uploading Files/Folders

The commands `scp` and `rsync` also uploads files and folders, just switch the [source] and [destination].

```
scp file <username>@schooner.oscer.ou.edu:/path/to/file                  # File Upload
```
```
scp directory <username>@schooner.oscer.ou.edu:/path/to/directory        # Folder Upload
```
<br />
```
rsync -avuim file <username>@dtn2.oscer.ou.edu:/path/to/file         # File Upload
```
```
rsync -avuim folder <username>@dtn2.oscer.ou.edu:/path/to/directory  # Folder Upload
```
<br />

