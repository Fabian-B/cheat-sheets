# checking for updates
'dnf upgrade'
installs all updates that **can** be installed. (dependencies might prevent installation of updates)

'dnf check-update'
used to check wich installed packages have updates available.(ingnores missing dependencies and therefor does not install them.)

'