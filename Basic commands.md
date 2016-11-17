## Installing software
`yum search [keyword/packagename]`
Search for the desired software.
`yum install [packagename]`
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

`usermod -aG [groupname] [username]`
Adds the specified user to another group.



`ls /[directoryname]/`
Lists all the files in the specified directory.

`ls -la`
Lists all files in de current directory including hidden files.
