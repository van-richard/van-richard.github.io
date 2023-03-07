---
layout: post
title: Creating Virtual Environments 
description: References to Conda commands for Package Management
---

### Table of Contents

1. [Conda Commands](#conda-commands)
2. [Example with AmberTools](#example-with-ambertools)

### Conda Commands

Creating a new virtual environment.

```
conda create -n <name>                          # Create New environment
conda create -n <name> python=<version-number>  # Specific Python version
```
<br />
Running the new environment.

```
conda activate <name>
```
<br />
In your new activated environment, you can now install needed packages.

```
conda install <package-name>                 # Install Package
conda install -c conda-forge <package-name>  # Install package from a specific channel (-c)
```
<br />
To leave a virutal environment.

```
conda deactivate
```
<br />
Deleting conda environments and related packages.

```
conda env remove -n <name>
```
<br />
List available environments.

```
conda env list
```
<br />
List packages within an environment.

```
conda activate <name>
conda list
```
<br />

### Example with AmberTools

```
conda create -n ambertools
conda activate ambertools
conda install -c conda-forge ambertools=22 compilers
```