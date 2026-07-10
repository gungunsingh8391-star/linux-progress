## df
Use_Case: list the free space and all directories on disk drives

## free
Use_Case: free memory on system.

## Linux follows a hierarchical directory structure.
almost every command follows this: command -option arguments (ex, tar -czf backup.tar.gz /home/user/documents)

##cd -
Use_Case: to get back on previous directory.

##cd ~user_name 
Use_Case: to switch b/w users.

## ls ~ /usr
use_case: to display multiple lists (eg, root user and /user)

## options with commands (can be used combined):
1. -a for displaying hidden files, denoted by a period.
2. -A does not list current and parent directory.
3. -h for human-readable output.
4. -l for long output
5. -d for listing directories and their content only.
6. -F for classifying the files and folders.
7. -r for reversing the output
8. -s for sorting result by file size.
9. -t for sorting by modification time.
10. -h for help screen.
11. -q to quit.
12. -i for inode number.
13. -a copies a folder exactly as a carbon copy, preserving all its original permissions, timestamps, and links.
14. -i for interacting with user for confirmation.
15. -u for update. 
16. -v for verbose, displays information message.
17. -f for forcing the system for process.

## file filename
use_case: to determine the type of content the file and folder has.

## less filename
use_case: to view the text files. Use b to one page up, space for down, up and down arrows for lines, 
G and g to move to the end and starting of file, /characters for searching characters. 

## Linux has pointers to files to access them from various locations. 
## Hard link: 
ln target_file link_name

## Soft link: 
ln -s target_file link_name

## Identifying Commands

## type command
use_case: to display a command type, the shell will execute.

## whatis command 
use_case: display one line description of man page.

## zless
use_case: display the content of gzip-compressed text files.

## apropos 
use_case: search the man page names and descriptions for a specific keyword.

## info command
use_case: Display highly detailed, hyperlinked and multipage docs.

## alias name='string (separate by ;)' 
use_case: custom shortcut for long commands. 1st search if name is already exists, by using type. Use unalias to remove.

## Redirecting commands by using '>'
Use_case: command > filename. It will redirect 'stdout'. 

## Redirecting multiple commands by using '>>'
Use_case: follow { command 1; command 2;  command 3; } >> filename. It will redirect 'stdout'. 
To append both stdout and stderr, use  { command 1; command 2;  command 3; } &>> file.

## /dev/null (bit bucket)
use_case: a special file that vanishes the output or error. use it like { command 1; command 2; } >> log.txt 2> /dev/null. This will vanish error and append stdout to the file.

## Cat, Tac, Rev
1. cat displays stdout (something like less cmd, but pageless). Using cat '>'/'>>' file, will wait to write input and append to file.
2. tac is the reverse of cat, from last line to the first line.
3. rev will reverse lines characterwise.

## Pipeline operator (|)
command 1 | command 2 | command 3

## uniq command
Use_case: to remove the duplicate. Use with -d to see duplicates.

## wc filename
Use_case: display line, word and bytes. we can limit it by -l, and it will take stdin, in case of no arguments.

## grep pattern filename
Use_case: to match the text patterns in files. -i for ignoring case. -w for matching whole word. -v for print lines not matching pattern. -l for output only file names matching pattern.

## xargs
Use_case: read stdin and convert command-line arguments for other commands, very useful. 

## tee 
use_case: read stdin and show stdout as well as in one or multiple files at same time.

## id 
it will display the unique uid and gid of a user

## umask
use_case: it will display the unmask values; 0002 (Binary: 000 000 000 010) and 0022 (Binary: 000 000 010 010) is default. It determines the default permissions for newly created files and directories. 1 in umask → Remove permission. 0 in umask → Keep permission.

## chown 
use_case: used to change the ownership. Syntax is chown [owner][:[group]] file...

## ps command
use_case: used to view processes. TTY displayed in output identifies the terminal session that started a process. ps u is a user-oriented view and gives much more info than other options.
## ps x and ps aux command
In ps x, it displays all processes regardless of any terminal. ? indicates no controlling terminal. While in ps aux, VSZ (Virtual Memory Size) = total virtual memory reserved by the process, RSS = actual RAM used by process.

## top command
use_case: To view the more dynamic view of machine's activity. 

## nice command
use_case: sudo nice -n -level program_name. Level range is -20 to 19 (low priority, high niceness). Used to increase or decrease niceness of a process, but be careful increasing priority. Superuser may increase, and regular user mau decrease.

## renice command
use_case: used to adjust niceness of running command. Syntax: renice -n level pid.

## kill command
use_case: used to terminate programs that need killing. Syntax: kill %no or kill pid. It directly doesnt kill any process, it just sends them signal. I doesnt destroy any process. Example, kill -STOP PID,kill -18 PID,etc.

## nohup command
use_case: Run a process that continues running even after terminal is closed. It prevents SIGHUP (hang up) signal.

## killall command
use_case: to send signal to multiple processes, matching a specific program or username. Syntax: killall [-u user] [-signal] name... IT require sudo for sending signals.

## pstree command
It will display processes in a tree-like structure, showing parent-child relationships.

## vmstat command
Snapshot of system resource usage.
