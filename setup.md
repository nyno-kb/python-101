---
title: Setup
---
## How to Install Python on macOS
Python 2 comes preinstalled on older versions of macOS. This is no longer the case for current versions of macOS, [starting with macOS Catalina](https://developer.apple.com/documentation/macos-release-notes/macos-catalina-10_15-release-notes#Scripting-Language-Runtimes).

### How to Check Your Python Version on a Mac
To check which Python version you have on your Mac, first open a command-line application, such as [Terminal](https://realpython.com/courses/using-terminal-macos/).

> ## Tip
>
> Here’s how you open Terminal:
>
>   1. Press the **`⌘ Cmd`** + **`Space`** keys.
>   2. Type `Terminal`.
>   3. Press **`Enter ↩`**.
>
> Alternatively, you can open Finder and navigate to *Applications → Utilities → Terminal*.
{: .callout}

~~~
# Check the system Python version
$ python --version

# Check the Python 2 version
$ python2 --version

# Check the Python 3 version
$ python3 --version
~~~
{: .shell}

If you have Python on your system, then one or more of these commands should respond with a version number.

For example, if Python 3.11.4 were already set up on your computer, then the python3 command would display that version number:

~~~
$ python3 --version
Python 3.11.4
~~~
{: .shell}

> ## Notice
>
> When typing `python3 --version` the Terminal may give you a notice saying `no developer tools were found...` and give you a pop-up screen with the choice to install these develper tools.  
> **We recommend that you skip this installation as it is slow and tedious and should be solved by the Python installation process described below.**
{: .callout}

You’ll want to get the latest version of Python if any of these conditions is true:
* None of the above commands returns a version number.
* The only version you see displayed is in the Python 2.X series.
* You have a version of Python 3 that isn’t the latest available, which was version 3.8.4 as of this writing.

## Getting started with Google Colab

Since you will be working in Google Colab, we recommend that you read this introduction before taking this course:  
[https://colab.research.google.com/](https://colab.research.google.com/)

## How to Install Python on Windows
As mentioned above there are several ways of installing Python on your Windows computer. The following guide works by downloading the latest version of Python from [Python.org](link). But before we you do that it is a good idea to check whether a version on Python is already on your computer.

### How to Check Your Python Version on Windows
To check which Python version you have on Windows, first open a command-line application, such as [Windows PowerShell](https://realpython.com/courses/using-terminal-windows/).

> ## Tip
>
> Here’s how you open Windows PowerShell:
>
>   1. Press the **`⊞ Win`** key.
>   2. Type `PowerShell`.
>   3. Press **`Enter ↩`**.
>
> Alternatively, you can right click the start button and select PowerShell.
{: .callout}

~~~
# Check the system Python version by typing the following into the PowerShell
python --version
~~~
{: .python}

If you have Python installed then this command should respond with a version number:
~~~
python --version
Python 3.11.4
~~~
{: .python}

> ## Notice
>You’ll want to get the latest version of Python if any of these conditions is true:
>* The command above does not return a version number.
>* You have a version of Python 3 that isn’t the latest available, which was version 3.9.12 as of this writing.
{: .callout}


{% include links.md %}