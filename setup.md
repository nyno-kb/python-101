---
title: Setup
---
## How to Install Python on macOS
Python 2 comes preinstalled on older versions of macOS. This is no longer the case for current versions of macOS, [starting with macOS Catalina](https://developer.apple.com/documentation/macos-release-notes/macos-catalina-10_15-release-notes#Scripting-Language-Runtimes).

### How to Check Your Python Version on a Mac
To check which Python version you have on your Mac, first open a command-line application, such as [Terminal](https://realpython.com/courses/using-terminal-macos/).

> **Tip:** Here’s how you open Terminal:
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

When typing `python3 --version` the Terminal may give you a notice saying `no developer tools were found...` and give you a pop-up screen with the choice to install these develper tools.  
**We recommend that you skip this installation as it is slow and tedious and should be solved by the Python installation process described below.**

## Getting started with Google Colab

Since you will be working in Google Colab, we recommend that you read this introduction before taking this course:  
[https://colab.research.google.com/](https://colab.research.google.com/)


{% include links.md %}