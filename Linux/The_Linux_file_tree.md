# The Linux File tree
Many Linux distributions partially follow the **Filesystem Hierarchy Standard (FHS)**. May help to make Unix/Linux file system trees conform. 

##### man hier
Gives information about the file system hierarchy of your distribution.

##### /bin
Contains **binaries** for use by all users. I.e.: */bin/cat*.
Some applications also use */bin* to store their binaries.

##### /sbin
System binaries, many require root privilege, used to configure the OS.
I.e.: */sbin/ipconfig*

##### /lib
Contains shared libraries
Typically the Linux kernel loads kernel modules from */lib/modules/$kernel-version*
*/lib32* and */lib64* clarify the register size used during compilation.

##### /opt
Used to store optional software, mostly from outside the distribution repository.
Can contain a structure like /opt/wp/bin, /opt/wp/man, /opt/wp/lib, ... where 'wp' is the package name.

##### /boot
Contains all files needed to boot the computer.

##### /etc
Contains all of the machine specific configuration files.
Many times the name of a config file is the same as the application with *.conf* added as extension.

*/etc/init.d* is present on a lot of Linux distributions, contains scripts to start and stop **daemons**. The init way of starting and stopping is being replaced.

*/ect/X11/xorg.conf* is the config file for the graphical display.

*/etc/skel*, the skeleton directory is copied to the home directory of a newly created user. Usually contains hidden files like a .bashrc script.

*/etc/sysconfig*, not mentioned in the FHS, contains a lot of RHEL config files.

##### /home
Usually contains folders per user, commonly named afther the user. Used to store personal data. Also contains the user profile, containing many hidden files.

##### /root
Contains personal data and profile of the root user

##### /srv
Data that is served by your system. FHS allows storing cvs, rsync, ftp and www data in this location.

##### /media
Serves as a mount point for removable media devices such as CD, DVD, USB-attached devices.

##### /mnt
Should be empty and only used for temporary mount points

##### /tmp
Applications and users should use this folder to store temporary data when needed.

##### /dev
Is populated with files as the kernel is recognizing hardware. Common hardware such as hard disk devices are represented by device files in /dev.

TO BE CONTINUED.




