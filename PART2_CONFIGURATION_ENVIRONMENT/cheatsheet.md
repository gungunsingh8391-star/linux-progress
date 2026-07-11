## printenv
use_case: It shows only environment variables. It can also list a specific variable.

## set
use_case: It will show both shell variables and functions, as well as environment variables. 
# echo $Variable
can be used to know value of known variable. 

## Startup files
Bash starts and reads a series of configuration scripts called startup files to define default environment. Computer boots > systemd starts > Login manager / terminal starts > bash starts > bash reads startup files.

## Types of shell session
> Login shell session: prompted for username and password. Bash reads /etc/profile -> ~/.bash_profile or ~/.bash_login or ~/.profile. So, when you log in. Login -> .profile
> Non-Login shell session: typically occurs when launching a terminal in GUI with terminal emulator. Bash reads /etc/bash.bashrc -> ~/.bashrc. A new Bash terminal opens, Open Terminal -> .bashrc. This session inherits env var from parent process (like login shell)
> ~/.bashrc file is most important startup file as it is almost always read. Non-login shells read it by default and most startup files for login shells also read the ~/.bashrc file as well.

## Startup file
Inside "less ~/.profile", If the file "~/.bashrc" exists, then read the "~/.bashrc" file. So .bashrc is almost always executed. 
PATH variable: this is where linux finds commands. it actually searches a list of directories contained in this var. See ## Setting PATH variable. We can create dir in home to store our private programs, just call "bin".
