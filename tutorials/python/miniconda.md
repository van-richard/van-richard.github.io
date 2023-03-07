---
layout: post
title: Installing Miniconda  
description: Installation Guide for *Conda Package Management
---

In the future, you may come into the problem of needing multiple version of Python or Python Library. By installing Anaconda (or miniconda/miniforge) you will save yourself from a major headache.

In short:
- Anaconda is a open-source package manager for coding with Python. 
- Miniconda is the minimal installer of Anaconda.
- Miniforge is the community driven version of Miniconda.
<br />

*This tutorial will focus on installing Miniforge.*

<ol>
<li> First it is always helpful to have a dedicated "Programs/" folder if you don't already have one.</li>

{% highlight ruby %}
mkdir Programs 
cd Programs
{% endhighlight %}

<li>Clone the miniforge repository for your OS from GitHub.</li> 

{% highlight ruby %}
git clone https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-<YOUR-OS>.sh
{% endhighlight %}

<li>Now that the file is downloaded, run the installaton script and follow the instructions until you reach the question on installation location.</li>

{% highlight ruby %}
bash Miniforge3-<YOUR-OS>.sh 
/home/<username>/Programs/miniforge3 # We want to install Miniconda here
{% endhighlight %}

<li>When all is done, Conda will ask you to intialize</li>

{% highlight ruby %}
conda init
{% endhighlight %}

</ol>