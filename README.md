<p align="center">
<img src="https://github.com/TheWITProject/installation_guide/blob/main/wit-button.png?raw=true" alt="" height="150" width="150"/>
</p>
<h1 align="center">installation guide</h1>
<p align="center"><i>a choose-your-own-adventure guide to getting your development environment set up</i></p>
<br />

# Mac Users
➡️ Lucky you! Head straight to the [Brew section](#brew).


# Windows Users
➡️ Let's get you a Unix-like shell first. Head over to the [Windows Subsystem for Linux section](#windows-subsystem-for-linux).


# Windows Subsystem for Linux
We're going to install something called a subsystem, which is essentially a different operating system running within your main operating system. In this case, it's Linux, which is super dope if you are already familiar with Linux and also the headaches that come with trying to have a good development environment in Windows. Note that this is different from running a virtual machine or a container. It is more like we are running a live version of Linux with our favorite distribution (a distribution is a flavor of Linux, with many developers preferring different distros). 

WSL has a version 1 and version 2. We want the shinier, faster version, which is WSL 2. 
[We will use the Microsoft Docs to guide us through the install](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

First, follow the instructions to install WSL 1 before upgrading to WSL 2.

To open Powershell as an Administrator, search for `powershell` in your start menu and right click to `Run as Administrator`. If you are not running as an administrator, it will yell at you about `permission denied`
or `not allowed` or `could not complete`.

When you have finished installing WSL 2, install `Ubuntu 20.04` from the Windows store.

**NOTE 1** The tutorial will ask you to pick a distribution after installing WSL 1. We don't want to do that just yet. Continue to install WSL 2.

**NOTE 2** At the top, it notes that you can skip all the tedious steps and use a simple `wsl --install` command in your windows command prompt if you join the Windows Insiders Program. This is up to you to decide! Consider it a fun journey to update your OS and get new features for Windows. However, things could break so I recommend sticking with the more boring steps unless you are confident.
**NOTE 3** Remember to write down your login for the account you create at the end on your first run. You will need this and reinstalling sucks.

If that all worked, congrats! You can launch it by typing `wsl` in a command prompt, or by searching for `Ubuntu` in your start menu and launching it (although it might be a little slow to show things).

If you want, you can also go ahead and install the [Microsft Terminal](https://docs.microsoft.com/en-us/windows/terminal/get-started) which is like iTerm on Mac, but it has way more customizability as you can see from the pictures at the bottom of the Microsoft Docs. To make your terminal look cool, hit up @anoojpatel so he can nerd out about making it [cool](https://docs.microsoft.com/en-us/windows/terminal/custom-terminal-gallery/custom-schemes) or getting Powerline or awesome fonts. 

_**HOWEVER**_ if you run into version issues or error codes like `Installation failed with error 0x80070003`, check out the [troubleshooting](https://docs.microsoft.com/en-us/windows/wsl/install-win10#troubleshooting-installation) section. Better yet, message @anoojpatel or come to his office hours for help.

➡️ By now, you should have Linux running on your computer. Go to the [Brew section](#brew).


# Brew

### Brew for Mac Users

### Brew for Windows Users
Because we have Linux (specifically Ubuntu 20.04), we can follow the standard brew install steps in our terminal (make sure you have launched `wsl` or are running the Ubuntu terminal).

**Note**, you will need to run the install command as the `root` user, meaning the highest privileged user. To do so, type `sudo -s` and then type in the password you made for your log in when we installed WSL.

Go [here](https://brew.sh/) and run the command in your terminal to start the installation of brew.

➡️ Now go to the [Git section](#git).


# Git
_Instructions here..._

### Mac Users

### Windows Users
For WSL users, git should already be installed. Test this by typing `git` in the terminal to see a wall of options print out. If you don't see this, that's very strange. To fix this, just use brew to install it. Here is the the command: `brew install git`!

➡️ Now go to [Python section](#python3).


# Python3
_Instructions here..._

### Python3 for Windows Users on WSL
WSL will have Ubuntu 18.04 LTS, which luckily comes with Python 3.6 already installed, but it does not come with some of the modules that you may expect to get with other Python installations. We will still need to install `pip`, the standard package manager for Python, and `venv`, the standard module used to create and manage lightweight virtual environments.

Confirm that Python3 is already installed by opening your Ubuntu terminal and entering: `python3 --version`. This should return your Python version number. If you need to update your version of Python, first update your Ubuntu version by entering: `sudo apt update && sudo apt upgrade`, then update Python using `sudo apt upgrade python3`.

Install `pip` by entering: `sudo apt install python3-pip`.

Install `venv` by entering: `sudo apt install python3-venv`.

➡️ Mac users, head over to the [Postgres for Mac Users section](#postgres-for-mac-users). Windows users, head over to the [Postgres for Windows Users section](#postgres-for-windows-users).


## Postgres for Mac Users
_Instructions here..._
_Also Postico_


## Postgres for Windows Users
First, you'll want to install PostgreSQL onto WSL. To do so, follow [this](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-postgresql) instruction guide that Microsoft has laid out.

First, you'll want to install PostgreSQL onto WSL. To do so, follow [this](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-postgresql) instruction guide that Microsoft has laid out.

Also note that [psql](https://www.postgresql.org/docs/10/app-psql.html) is an interactive terminal you can install om the WSL terminal to play with the PostgreSQL database. Wow, that's a lot of terminalception! 😮

However, for our use case, we'd probably want to have a nice GUI to see our tables, so we'll have to use pgAdmin and get it to communicate to the database in the Linux Subsystem Environment. 

Here's what I did to connect Postgres database installed in WSL Ubuntu from Windows pgAdmin.

1. Launch Ubuntu in Windows via the Windows terminal by either typing `wsl` or opening it from the top tab.
2. Start Postgres in Ubuntu terminal: `sudo service postgresql start`
3. Download the latest [pgAdmin](https://www.pgadmin.org/download/pgadmin-4-windows/) and install in Windows (the latest version at this time of writing is v4.28).
4. Launch pgAdmin. A new tab in browser opens. Click on _Add New Server link_.
5. In the pop up _Create - Server_ window in the browser:
    General tab: set the name to localhost
    Connection tab: set host name/address to `localhost` and set password to `postgres`, which is the default. Click on _Save password?_
6. Save the setting and leave the rest of the fields as is.

That's it! That's how you connect to any datbase running on WSL that's on `localhost`. You may notice that when you were prompted to create a database earlier in the _WSL_ terminal, you may have set a password. Just change 
the password for _pgAdmin_ accordingly.

<p align=center><img src="https://i.stack.imgur.com/LOhGV.png" width=650 /></p?

