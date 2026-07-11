## Shell (BASH) Environment
1. Shell variables: bits of data placed by current shell instance. Disappear when bash is closed.
2. Environment variables: shared with program that bash starts.
3. Programmatic data such as Aliases and Shell Functions.
4. We can use printenv program and set builtin to examine inside bash. See in cheatsheet.md. But aliases can be viewed with "aliases" without arguments.


| Variable | Description |
| :--- | :--- |
| **USER** | Display user |
| **DISPLAY** | Which monitor/window should GUI programs use? |
| **EDITOR** | Default text editor |
| **SHELL** | User’s default shell program |
| **HOME** | Pathname of home directory, cd addresses this. |
| **LANG** | Define the character set and collation order of human language. |
| **OLDPWD** | Previous pwd |
| **PAGER** | Default paging program |
| **PATH** | Colon-separated list of dir, searched when enter executable program. |
| **PS1** | “Prompt string 1" is shell variable; contents of the shell prompt. |
| **TERM** | Terminal type, this variable sets the protocol to be used with our terminal emulator. |
| **TZ** | Specifies our time zone, maintained in UTC. |

## Setting PATH variable
The PATH variable is often set by the .profile startup file with this code: 
`PATH=$PATH:$HOME/bin`
PATH is modified to add the directory `$HOME/bin` to the end of the list, which is an example of parameter expansion. Now `$HOME/bin` is added to the list of directories searched.

## export command
use_case: to convert shell var to env var. `export PATH` to make the content of PATH var available to child.
