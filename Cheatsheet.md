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
use_case: custom shortcut for long commands. 1st search if name is alreay exixts, by using type. Use unalias to remove.
