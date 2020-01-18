# Usage

### Basics

{% hint style="info" %}
In this guide you may see `py` or `python` used interchangeably. They mean the same thing, and vary only to the documenter's OS allegiance.
{% endhint %}

#### Windows

Use `py -3 <program name>` for code designed to run with Python 3.\*, and `py -2 <program name>` for code designed to run with Python 2.\*. Try to keep everything on Python 3. 

#### Macintosh + Linux

{% hint style="warning" %}
Oftentimes a given linux distribution will automatically choose `python3` or `python2` to alias to `python`, for example Ubuntu's `python` command runs `python2`, while Fedora and Arch run `python3.` As such it is good practice to always use python3 unless you know what you're doing.
{% endhint %}

Use `python3` for code designed to run with Python 3.\*, and `python2` for code designed to run with Python 2.\*. Try to keep everything on Python 3.x.

### Running a script

{% hint style="info" %}
As Python is an interpreter, a `.py` is usually called a script. Nobody will care if you call it a program. In fact, most will make this mistake, even the Programming Lead.
{% endhint %}

Any file with the `.py` extension can be run with Python. Simply run `python <name of file>.py`

### The Shell

If you don't specify a file to run \(ex `python`\), you'll get an interactive shell. You can enter commands as if it were a real program in real time. It's not generally used, but can be useful for testing something \(for example if you installed a package correctly\) in a pinch.

To exit either use exit\(\) or quit\(\). It doesn't matter which.

