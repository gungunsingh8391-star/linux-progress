## ESSENTIAL THEORY OF LINUX

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
