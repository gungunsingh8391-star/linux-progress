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
