# Package installation w/ pip

### Introduction

Extra libraries can be added to Python to supplement what you write. Although by no means definitive, this page should get you ready to understand how to at least deal with them - they're a major part of what we do.

### PIP

Python uses their own custom package manager called `pip` to manage what extras are installed. However pip may not by default be installed, nor will the usual `pip3 install <name of package>` work.

{% hint style="danger" %}
For users of some Linux Distributions, especially those Arch based, should never use pip to install a package. See the your distro's wiki's for more.
{% endhint %}

#### Installation \(System agnostic\)

Head [here](https://bootstrap.pypa.io/get-pip.py) and download get-pip.py, and run it using python 3. After running you should be able to run \(as administrator\) `python -m pip install <name of package>.` 



