---
title: Setup
---
 
[How to Install Python on macOS](#how-to-install-python-on-macos)

[How to Install Python on Windows](https://pryn-kb.github.io/python-101/setup.html#how-to-install-python-on-windows)

#Running Python


Before you can run, you must first walk (or slither).  
In order to get Python to run on your machine, you need to either download it directly or run it
 through an intermediary.  There are many different ways to do this.  
 We will highlight three possibilities, but for those that prefer another method, 
 RealPython has compiled a broader list.  Be aware that one has a limited number of ‘reads’
 before the RealPython website requests you make an account with them.  
 You can get around this issue by opening a ‘private browsing’ tab and reading it there. 
 The abovementioned guide can be found here : https://realpython.com/installing-python/

###Method 1: Installing Python and Jupyter Notebooks

The first of the three options we would like to highlight is installing 
Python and Jupyter Notebooks.  This installs the software directly on to your computer.  
It is slightly technical, as you will have to initiate the program through your computer's terminal/powershell, 
but once running it is far less finicky than the other options with respect to uploading 
or downloading files that you might use in your coding.  
A detailed set of instructions for both Mac and PC users can be found further down this page.

###Method 2: Google Colab

Google Colab, along with ERDA, is perhaps the easiest of these three options to get up and
 running, as all it requires is a Google account (i.e. a Gmail login).  
 After you login, you simply create a new notebook and start coding.  
 Uploading and downloading files can be finicky on this medium, as they need to be uploaded again for each coding session in the free version.  
 All uploaded files are erased when you close your session or if your session times out.  You can read more about Google Colab at this link:

https://colab.research.google.com/?utm_source=scs-index

###Method 3: CUs ERDA

Copenhagen University provides its students and staff with access to its 
Electronic Research Data Archive (ERDA).  ERDA includes a built-in copy of Jupyter Notebooks,
 which runs the newest version of Python.  Simply select the Jupyter Notebooks icon after logging in, 
 then select Start DAG, and continue on to your coding space.  
 Be aware that ERDA cannot read local files off of your computer so you must, like 
 Google Colab, upload any files you wish to work with.  Unlike Google Colab, however, 
 ERDA will maintain your files over time, saving you the trouble of worrying about different 
 file pathways in your code.  ERDA's self description as well as its terms and conditions can 
 be read here: 

https://www.erda.dk/

## How to Install Python on macOS
Python 2 comes preinstalled on older versions of macOS. This is no longer the case for current versions of macOS, [starting with macOS Catalina](https://developer.apple.com/documentation/macos-release-notes/macos-catalina-10_15-release-notes#Scripting-Language-Runtimes).  
No mattter which version of macOS you have installed, we would still like you to install Python 3.

### How to Check Your Python Version on a Mac
To check which Python version you have on your Mac, first open a command-line application, such as [Terminal](https://support.apple.com/guide/terminal/welcome/mac).

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
<br>
<br>
Check the system Python version:
~~~
python --version
~~~
{: .python}

Check the Python 2 version:
~~~
python2 --version
~~~
{: .python}

Check the Python 3 version:
~~~
python3 --version
~~~
{: .python}
<br>
<br>
If you have Python on your system, then one or more of these commands should respond with a version number.

For example, if Python 3.11.4 were already set up on your computer, then the python3 command would display that version number:

~~~
python3 --version
~~~
{: .python}

~~~
Python 3.11.4
~~~
{: .output}

> ## Notice
>
> When typing `python3 --version` the Terminal may give you a notice saying `no developer tools were found...` and give you a pop-up screen with the choice to install these develper tools.  
> **We recommend that you skip this installation as it is slow and tedious and should be solved by the Python installation process described below.**
{: .callout}

You’ll want to get the latest version of Python if any of these conditions is true:
* None of the above commands returns a version number.
* The only version you see displayed is in the Python 2.X series.
* You have a version of Python 3 that isn’t the latest available, which was version 3.11.4 as of this writing.

### How to Install From the Official Installer
Installing Python from the official installer is the most reliable installation method on macOS. It includes all the system dependencies needed for developing applications with Python.

You can install from the official installer in two steps.

#### Step 1: Download the Official Installer
Follow these steps to download the full installer:

1. Open a browser window and navigate to the Python.org [Downloads page for macOS](https://www.python.org/downloads/mac-osx/).
2. Under the “Python Releases for Mac OS X” heading, click the link for the ***Latest Python 3 Release - Python 3.x.x***. As of this writing, the latest version was Python 3.11.4.
3. Scroll to the bottom and click ***macOS 64-bit installer*** to start the download.

When the installer is finished downloading, move on to the next step.

#### Step 2: Run the Installer
Run the installer by double-clicking the downloaded file.

Follow these steps to complete the installation:

1. Press ***Continue*** a few times until you’re asked to agree to the software license agreement. Then click ***Agree***.
2. You’ll be shown a window that tells you the install destination and how much space it will take. You most likely don’t want to change the default location, so go ahead and click ***Install*** to start the installation.
3. When the installer is finished copying files, double-click the ***Install Certificates*** command in the finder window to make sure your SSL root certificates are updated.

Congratulations—you now have the latest version of Python 3 on your macOS computer!





## Getting started with Google Colab

Since you will be working in Google Colab, we recommend that you read this introduction before taking this course:  
[https://colab.research.google.com/](https://colab.research.google.com/)

## How to Install Python on Windows
As mentioned above there are several ways of installing Python on your Windows computer. The following guide works by downloading the latest version of Python from [Python.org](https://www.python.org/). But before we you do that it is a good idea to check whether a version on Python is already on your computer.

### How to Check Your Python Version on Windows
To check if you have any version of Python and which Python you have on Windows, first open a command-line application, such as [Windows PowerShell](https://realpython.com/courses/using-terminal-windows/).

> ## Tip
> Here’s how you open Windows PowerShell:
>
>   1. Press the `**⊞ Win**` key.
>   2. Type `PowerShell`.
>   3. Press `Enter ↩`.
>
> Alternatively, you can right click the start button and select PowerShell.
{: .callout}


Check the Python version by typing the following into the PowerShell
~~~
python --version
~~~
{: .python}

If you have Python installed then this command should respond with a version number:
~~~
Python 3.11.4
~~~
{:  .output}

> ## Notice
>If you don't have a version of Python on your computer the above command will launch Microsoft Store where you can find a Python application. ***Do not download this version of Python!*** Instead follow the steps below.  
{: .callout}

You’ll want to get the latest version of Python if any of these conditions is true:
* The command above does not return a version number.
* You have a version of Python 3 that isn’t the latest available, which was version 3.9.12 as of this writing.

### How to Install From the Official Installer
Installing Python from the official installer is the most reliable installation method on Windows. It includes all the system dependencies needed for developing applications with Python. However, it can cause some trouble, so read the following guide carefully. 

You can install from the official installer in two steps.

#### Step 1: Download the Official Installer
Follow these steps to download the full installer:

1. Open a browser window and navigate to [Python.org](https://www.python.org/).
2. In the drop down menu called "Downloads" click the link for the ***Latest Python 3 Release - Python 3.x.x***. As of this writing, the latest version was Python 3.11.4.
3. The download should start instantly.

When the installer is finished downloading, move on to the next step.

#### Step 2: Run the Installer
Run the installer by double clicking on the downloaded .exe file.

Follow these steps to complete the installation:

1. Select the box **"Install launcher for all users"** this allows all users of the computer to use the Python launcher application
2. Select the box **"Add Python 3.x to PATH"** this enables you to launch Python from the command line
3. Click **"Install Now"**
4. Click the **"Disable path length limit"**. This removes the limitation of the path lenghts and can smoothe over any issues in the future with the path length
5. Press close to finish the installation

Congratulations—you now have the latest version of Python 3 on your computer!

> ## Tip
>If you did not click **"Add Python to PATH"** this can be fixed by following these steps:
> 1.	Open the folder where you downloaded the Python install file
> 2.	Double click on the Python install file
> 3.	Click **"Modify"**
> 4.	You will see **"Optional features"**
> 5.	Click "Next"
> 6.	Select **"Add python to environment variables"**
> 7.	Click "Install"
{: .callout}

### Check your version of Python
Now that you have installed Python, it is a good idea to check if it was done succesfully, before we move on to installing Jupyter Lab. Jupyter Lab is the IDE we will use for writing code during the course. 

Open the PowerShell and type in: 
~~~
python --version
~~~
{: .python}

Now this should return the version of Python you have just installed
~~~
Python 3.11.4
~~~
{:  .output}

### Jupyter Lab 
Now you need to install Jupyter Lab, the Inetegrated development enviroment (IDE) we will be using in this course. We will install this from the PowerShell using PIP. PIP is a package manager which allows you to easily install and manage Python libraries and packages - don't worry if this doesnt make a lot of sense right now, we will get back to what that means in the course. 
Before moving on, it is therefore a good idea to check the PIP version - this should have been installed together with Python. If this did not happen see the Tip box below.
Type the following in the PowerShell: 
~~~
pip --version
~~~
{: .python}
If the command returns e.g. pip 21.2.4 you have it corrently installed - otherwise move to the Tip box below before you continue
Now you can simply type: 
~~~
pip install jupyterlab
~~~
{: .python}
An installation will start in the PowerShell - when it finishes type the following and the notebook will launch 
~~~
jupyter lab
~~~
{: .python}
This opens a browser window with a control panel. 

Now you are ready to learn how to code in Python!





 

{% include links.md %}