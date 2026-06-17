## df
Use_Case: list the free space and all directories on disk drives

## free
Use_Case: free memory on system.

## Linux follows a hierarchical directory structure.
## almost every command follows this: command -option arguments (ex, tar -czf backup.tar.gz /home/user/documents)

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
-d for listing directories and their content only/\.
-F for classifying the files and folders.
-r for reversing the output
-s for sorting result by file size.
-t for sorting by modification time.
-h for help screen.
-q to quit.

## file filename
use_case: to determine the type of content the file and folder has.

## less filename
use_case: to view the text files. Use b to one page up, space for down, up and down arrows for lines, 
G and g to move to the end and beginning of file, /characters for searching characters. 

## Core System Directories
/: The starting point of the directory tree. Every single file and folder lives under this.
/bin: Essential user command binaries (like ls, cp, and ping) needed for the system to run.
/sbin: System binaries used primarily by the root administrator for maintenance (like iptables, fdisk, and reboot).
/boot: Static files needed to start the computer, including the Linux kernel and the GRUB bootloader.
/etc: Host-specific system-wide configuration files. This is where we change network settings, user lists, and application configs.

## User and Application Directories
/home: Users' personal folders.
/root: The separate, private home directory specifically for the root (administrator) user.
/usr: The largest directory, containing user binaries, libraries, documentation, and source code for secondary programs.
/opt: Optional add-on software packages. Commercial or third-party software (like Google Chrome or Discord) often installs here.

## Virtual and Runtime Directories
/dev: Device files. In Linux, hardware devices (like hard drives, keyboards, or disk1.img) are represented as files here.
/proc: A virtual filesystem providing process and kernel information. It does not exist on the disk, it lives in system memory.
/sys: Another virtual directory that exports information about hardware devices, drivers, and kernel subsystems.
/run: Volatile runtime data describing the system since it booted (like currently logged-in users and active daemons). 

## Temporary and Variable Directories
/var: Variable data files that change constantly while the system runs, such as system logs (/var/log), mail caches, and databases.
/tmp: Temporary files created by applications. Files here are usually deleted automatically when the system reboots.
/mnt: A temporary mount point where administrators can manually attach filesystems or external drives.
/media: Automatic mount points for removable storage media, like USB thumb drives or external hard disks.
/srv: Site-specific data served by the system, such as files for a web server or an FTP server.
/lib & /lib64: Shared libraries essential for the binaries in /bin and /sbin to function.


