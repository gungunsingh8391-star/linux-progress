## ESSENTIAL THEORY OF LINUX

## Core System Directories
1. /: The starting point of the directory tree. Every single file and folder lives under this.
2. /bin: Essential user command binaries (like ls, cp, and ping) needed for the system to run.
3. /sbin: System binaries used primarily by the root administrator for maintenance (like iptables, fdisk, and reboot).
4. /boot: Static files needed to start the computer, including the Linux kernel and the GRUB bootloader.
5. /etc: Host-specific system-wide configuration files. This is where we change network settings, user lists, and application configs.

## User and Application Directories
1. /home: Users' personal folders.
2. /root: The separate, private home directory specifically for the root (administrator) user.
3. /usr: The largest directory, containing user binaries, libraries, documentation, and source code for secondary programs.
4. /opt: Optional add-on software packages. Commercial or third-party software (like Google Chrome or Discord) often installs here.
5. /usr/local: The location where system administrators install programs locally. Programs compiled from source code go here so they do not overwrite core system files.

## Virtual and Runtime Directories
1. /dev: Device files. In Linux, hardware devices (like hard drives, keyboards, or disk1.img) are represented as files here.
2. /proc: A virtual filesystem providing process and kernel information. It does not exist on the disk, it lives in system memory.
3. /sys: Another virtual directory that exports information about hardware devices, drivers, and kernel subsystems.
4. /run: Volatile runtime data describing the system since it booted (like currently logged-in users and active daemons). 

## Temporary and Variable Directories
1. /var: Variable data files that change constantly while the system runs, such as system logs (/var/log), mail caches, and databases.
2. /tmp: Temporary files created by applications. Files here are usually deleted automatically when the system reboots.
3. /mnt: A temporary mount point where administrators can manually attach filesystems or external drives.
4. /media: Automatic mount points for removable storage media, like USB thumb drives or external hard disks.
5. /srv: Site-specific data served by the system, such as files for a web server or an FTP server.
6. /lib & /lib64: Shared libraries essential for the binaries in /bin and /sbin to function.

## Hard link: 
1. The inode no remains the same for both the original file and hardlink, so the data can be accessed if the original file gets deleted.
2. Changes occur in orginal file and hardlink.
3. limitations: that cannot be linked to directories and cannot cross different file systems and partitions.

## Soft link: 
1. A soft link is essentially a shortcut.
2. It stores the path string of the target file.
3. owns a unique inode number and shows up as a link type (l).
4. If you delete the original file, the soft link becomes broken.
5. Limitations: can be linked to directories and cannot cross different filesystems or external drives.

## Wildcards:
special characters help rapidly specify group of file name.

1. * : match any char including none.
2. ? : match single char.
3. [char] : match any char, member of set chars.
4. [!char] : match any char, not member of set chars.
5. [[:class:] : match any char, member of specified class.

## [:alnum:], [:alpha:], [:digit:], [:lower:], [:upper:]
Use ";" for one command on a line by separating each command.

## Type of commands
1. Aliases are shortcuts of long commands, ex, ls -l -> ll
2. Shell Builtins, which are built-in commands that don't need any external software to be executed.
3. Executable Programs are external software, when run, system executes their binaries.

## File descriptor
The three most important file descriptors are:
1. STDIN (standard input, <)
2. STDOUT (standard output, >)
3. STDERR (Standard error, >)
The shell redirection operators work on FDs.

## Redirection operator (>) vs Pipeline operator (|)
1. '>' connects a command with a file. Be careful using this.
2. | will take the stdout of a command as stdin for another command. 
we can use filters with |, ex: sort, uniq, uniq -d, tee, grep.

## Types of Expansions:
1. Pathname expansion (globbing): expands wildcards (eg., *, [], ?) into matching filenames and directories in the current path.
2. Tilde expansion (~): current user or the home user, when used with echo.
3. Arithmetic Expansion: $((expression)), where expression can contain only whole numbers, with basic operators.
4. Brace expansion: can create multiple text strings from a pattern containing braces, can also be nested. Such as, for mkdir {1..15}, echo {Z..A}.
5. Parameter Expansion: replaces a variable reference with its value, allowing variable substitution and manipulation in shell commands.

## Command substitution (`` or $()):
allows the use of the output of a command as expansion.

## Quoting (selectively suppress unwanted expansion)
Note: arithmetic expansion, parameter expansion and command substitution will still take place.
> to supress all expansions, use single quotes.

## Escaping characters
use backslash to escape a single character from double quotes. -e option to echo will enable interpretation of escape sequences.

## id commands:
1. user accounts are defined in /etc/passwd and groups in /etc/group.
2. User passwords are stored in /etc/shadow.
3. Information of each user (uid, gid, home directory, login shell, real name) is stored in /etc/passwd.
4. Information of group (uid, group name, group members) is stored in /etc/group file.

## System users
Linux has regular user accounts and system user accounts.
The superuser (root) always have uid = 0.
Other system users are created for running system services and applications securely.

## File Types
'-' as regular file, d as directory, l as link but with dummy values, c as characters referring to data moves one byte at a time such as ll /dev/null and b as block referring to data moves one chunk (block) at a time such as ll /dev/sda.

## chmod command
It supports octal number representation (represents 3 binary digits) and symbolic representation.
-> Common octal to binary mapping are 7(rwx), 6(rw-), 5(r-x), 4(r--), 0(---).
-> Symbolic representaion:  chmod Symbolic Notation are u for user, g for group, o for others and a for all (default), + for permission added, - is removed and = is for setting specific permissions, removing the earlier set permissions. (examples: go=rw; u+x,go=rx)
-> less used permissions: setuid bit (octal 4000) [used as chmod u+s program], setgid bit (octal 2000) [used as chmod g+s dir] and stick bit (octal 1000) [used as chmod +t dir].

## sudo usermod -aG sudo name 
It will give the other user the privilege of sudo. usermodify -append, add the user to sudo group, name for modigying the user.

## Linux PROCESSES
Init launches 'systemd ', which starts all system services. Daemon programs runs in background having a UI.
> STAT in 'ps x' reveals current status of process. S = sleeping, R = running or ready to run, D = uninterruptible sleep waiting for I/O, T = stopped, Z = zombie process which is terminate but not cleaned by parent process. < high-priority process 'less nice'. N = low-priority process 'nice'.

## top command structure
Summary displays current time, uptime (since started), currently logged users, avg CPU load over in last 1 min, 5 min, 15 min. Tasks summarise processes and their states. CPU (s) describes performing, eg., us (user processes), system proc., ni (nice proc.), idle (id), hi (hardware interrupts), wa(waiting for i/o). Mem shows physical RAM usage and Swap shows virtual memory usage.

## Running process in background:
To do so, use & sign. It can let us to use shell and keep running the process in bg. The job no and PID is printed. 'jobs' command can be used to see running process. 'fg %1' eg, fg followed by % and job no, can be used to return process to foreground. 

## Stopping process in background:
Stopping a process without terminating which is to stop a foreground process in bg, use ctrl z. we can resume the process in bg, by using 'bg %1'.

## Responding signal by processes
Processes receive signals from the operating system (or other processes) and can handle many of them by executing predefined actions.
o Common Signals: SIGINT (Ctrl+C) → interrupt, SIGTSTP (Ctrl+Z) → stop temporarily, SIGTERM → terminate gracefully, SIGKILL (kill -9) → terminate immediately (cannot be caught or ignored).
| No. | Signal | Work                         |
| --- | ------ | ---------------------------- |
|  1  |  HUP   | Reload your settings         |
|  2  |  INT   | Ctrl+C → Stop now            |
|  9  |  TERM  | Please close politely        |
|  15 |  KILL  | Force close immediately      |
|  18 |  STOP  | Pause                        |
|  19 |  CONT  | Continue                     |
|  20 |  TSTP  | Ctrl+Z → Pause from keyboard |
