<p align="center">
<img src="https://github.com/TheWITProject/installation_guide/blob/main/wit-button.png?raw=true" alt="" height="150" width="150"/>
</p>
<h1 align="center">installation guide</h1>
<p align="center"><i>a choose-your-own-adventure guide to getting your development environment set up</i></p>
<br />

## Mac Users
Lucky you! Head straight to the [Brew section](#brew).


## Windows Users
Let's get you a Unix-like shell first. Head over to the [Windows Subsystem for Linux section](#windows-subsystem-for-linux).


## Windows Subsystem for Linux
We're going to install something called a Subsystem, which is essentially a version of a different OS running within your main OS.
In this case, it's Linux! Which is super dope if you are familiar with Linux and the headaches of trying to have a good development 
environment in Windows. We can midigate that if we can just run Linux right under Windows.
Note, this is different from running a VM, or a container, since this is essentially running Linux right next to the Windows OS. This
means it's like having a live version of Linux with your favorite distribution (distribution is a flavor of Linux, with many developers preferring
different distros). 

WSL exists in version 1 and version 2. We want the shinier, faster version, which is WSL 2. 
[We will use the Microsoft Docs to help us install](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to help us.


We will first follow the instructions to install WSL 1, since we need to install that first and then upgrade it to WSL 2.

To open Powershell as an Administrator, search for `powershell` in your start menu, and right click to `Run as Administrator`. It will yell at you about `permission denied`
or `not allowed` or `could not complete` if you're not running as administrator.

Also, install `Ubuntu 20.04` from the Windows store when we get to the end of installing WSL 2.

**NOTE 1** The tutorial will ask you to pick a distirbution after installing WSL 1. We don't want to do that just yet, rather we 
should continue to install WSL 2. 
**NOTE 2** At the top, it notes that you can skip all the tedious steps and use a simple `wsl --install` command in your windows command prompt by joining 
the Windows Insiders Program. This is up to you to decide. Consider it a fun journey to update your OS and get new features for Windows, however, things could break
so I recommend, unless you're confident in installing stuff on your computer, stick with the more boring steps.
**NOTE 3** Remember to write down your login for the account you create at the end on your first run. Reinstalling sucks.

If that all worked congrats! you can launch it by typing `wsl` in a command prompt, or searching for `ubuntu` in your start menu and launching it (might be a little slow to show things).
Also if you want, you can go ahead and install the [Microsft Terminal](https://docs.microsoft.com/en-us/windows/terminal/get-started) which will be like iTerm on Mac, but it has way more customizability as you can see from the pictures
at the bottom of the Microsoft Docs. To make your terminal look cool, hit up @anoojpatel so he nerd out about making it [cool](https://docs.microsoft.com/en-us/windows/terminal/custom-terminal-gallery/custom-schemes) or getting Powerline or having awesome Fonts. 

_**HOWEVER**_ if you ran into version issues, or error codes like `Installation failed with error 0x80070003` Check out the [troubleshooting](https://docs.microsoft.com/en-us/windows/wsl/install-win10#troubleshooting-installation) section. Better yet, message @anoojpatel or come to his office hours for help.

By the end of it, you'll have Linux running on your computer!

Now go to the [Brew section](#brew).


## Brew

### Brew for Mac Users

### Brew for Windows Users
Because we have Linux (Specifically Ubuntu 20.04) we can follow the brew install steps in our terminal (make sure you launched `wsl` or are running the ubuntu terminal).
**Note**, you will need to be `root` user, meaning the highest privileged user. To do so, type `sudo -s` and type in the password you made for your log in when we installed WSL.

Go [here](https://brew.sh/) and run the command in your terminal to start the installation of brew.

Now go to the [Git section](#git).


## Git
_Instructions here..._

### Mac Users

### Windows Users
For WSL users, git should already exist. Test this by typing `git` in the terminal to see a wall of options print out. If you don't, that's very strange. To fix that just use
brew to install it via `brew install git`!

Now go to [Python section](#python3).


## Python3
_Instructions here..._

Mac users, head over to the [Postgres for Mac Users section](#postgres-for-mac-users). Windows, head over to the [Postgres for Windows Users section](#postgres-for-windows-users).


## Postgres for Mac Users
_Instructions here..._
_Also Postico_


## Postgres for Windows Users
_Instructions here..._
_Also pgAdmin_
