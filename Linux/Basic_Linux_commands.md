## Man pages

`man [command]`
Lists all the options and their explanation, available to use with a certain command.
i.e.: man usermod gives all options to use with usermod.

`man -k [string]` Lists all man pages containing a string.

## Installing software
`dnf search [keyword/packagename]`
Search for the desired software.
`dnf install [packagename]`
Install the software/package.

## Checking for updates

`dnf upgrade`
Installs all updates that **can** be installed. (dependencies might prevent installation of updates)

`dnf check-update`
Used to check wich installed packages have updates available.(ingnores missing dependencies and therefor does not install them.)

## Users and groups

`useradd [username]`
Adds a user with the specified name and default settings.

`su - [username]`
Log in as the specified user. (su = substitute user)

`passwd [username]`
Changing the password of a user, also used for initial setup.

`usermod -L [username]` `usermod -U [username]`
Respectively locks and unlocks a useraccount.

`usermod -aG [groupname] [username]`
Adds the specified user to another group.

`usermod -G [groupname],[groupname] [username]`
A list of supplementary groups wich the users is also member of.
If the user is currently member of a group wich is not listed, the user will be removed from the group.

`groups [username]`
Lists all groups wich the specified user is member of.

`userdel [username]`
Used to delete a useraccount. The option `-r` also removes the homedir. View man page for all options.

`groupadd [groupname]`
Adds a group with the specified name.

`groupmod [groupname]`
Change settings of a specified group.

`groupdel [groupname]`
Delete a specified group. 

## file browsing and manipulating

`ls /[directoryname]/`
Lists all the files in the specified directory.

`ls -la`
Lists all files in de current directory including hidden files.
