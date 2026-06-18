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
-a for displaying hidden files, denoted by a period.
-A does not list current and parent directory.
-h for human-readable output.
-l for long output
-d for listing directories and their content only.
-F for classifying the files and folders.
-r for reversing the output
-s for sorting result by file size.
-t for sorting by modification time.
-h for help screen.
-q to quit.
-i for inode number.
-a copies a folder exactly as a carbon copy, preserving all its original permissions, timestamps, and links.
-i for interacting with user for confirmation.
-u for update. 
-v for verbose, displays information message.
-f for forcing the system for process.

## file filename
use_case: to determine the type of content the file and folder has.

## less filename
use_case: to view the text files. Use b to one page up, space for down, up and down arrows for lines, 
G and g to move to the end and beginning of file, /characters for searching characters. 

## Linux has pointers to files to access them from various locations. 
## Hard link: 
ln target_file link_name

## Soft link: 
ln -s target_file link_name

