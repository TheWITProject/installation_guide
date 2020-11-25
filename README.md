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
_Instructions here..._

Now go to the [Brew section](#brew).


## Brew
_Instructions here..._

Now go to the [Git section](#git).


## Git
_Instructions here..._

Now go to [Python section](#python3).


## Python3
_Instructions here..._

### WSL and Installing Python
WSL will have Ubuntu 18.04 LTS, which luckily comes with Python 3.6 already installed, but it does not come with some of the modules that you may expect to get with other Python installations. We will still need to install pip, the standard package manager for Python, and venv, the standard module used to create and manage lightweight virtual environments.

Confirm that Python3 is already installed by opening your Ubuntu terminal and entering: `python3 --version`. This should return your Python version number. If you need to update your version of Python, first update your Ubuntu version by entering: `sudo apt update && sudo apt upgrade`, then update Python using `sudo apt upgrade python3`.
What you really need to install is `pip` and `venv`.

Install pip by entering: `sudo apt install python3-pip`. Pip allows you to install and manage additional packages that are not part of the Python standard library.

Install venv by entering: sudo apt install python3-venv.
Mac users, head over to the [Postgres for Mac Users section](#postgres-for-mac-users). Windows, head over to the [Postgres for Windows Users section](#postgres-for-windows-users).


## Postgres for Mac Users
_Instructions here..._
_Also Postico_


## Postgres for Windows Users
First You'll want to install PostgreSQL onto your WSL. To do so, follow [this](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database#install-postgresql) instruction guide that Microsoft has laid out. 
Also note [psql](https://www.postgresql.org/docs/10/app-psql.html) is an interactive terminal that runs in our WSL terminal to play with the PostgreSQL database (wow that's a lot of terminalception).

However, for our use case, we'd probably want to have a nice GUI to see our tables, so we'll have to use pgAdmin and get it to communicate to the database in the Linux Subsystem Environment. 

Here's what I did to connect Postgres DB installed in WSL Ubuntu from Windows pgAdmin.

1. Launch Ubuntu in Windows via the windows terminal and either typing `wsl` or opening it from the top tab.
2. Start postgres in Ubuntu terminal: `sudo service postgresql start`
3. Download the latest [pgAdmin](https://www.pgadmin.org/download/pgadmin-4-windows/) and install in Windows (Latest at this time of writing is v4.28).
4. Launch pgAdmin, a new tab in browser opens; click on _Add New Server link_.
5. In the popup _Create - Server_ window in the browser:
    General tab: I set Name to localhost
    Connection tab: I set Host name/address to `localhost`, set Password to `postgres`, which is the default, click on _Save password?_
    I save the setting, leaving the rest of the fields as is
That's it, that's how you connect to any DB running on WSL that's on `localhost`. You may notice that when you were prompted to create a DB earlier in the _WSL_ terminal, you may have set a password. Just change 
the password for _pgAdmin_ accordingly.
![Image of Creating Server link to DB](https://i.stack.imgur.com/LOhGV.png)

