usm
===

Unified Slackware Package Manager

A slackware package manager that resolves dependencies and searches across multiple slackware repositories.
It includes a CLI (/usr/bin/usm) and GUI (/usr/bin/usmgui)

Beta only runs on slackware 14.1

By default the build strips all comments

Example build usages:

    make STRIP_COMMENTS=false DESTDIR=/tmp/usmbuild install
    
    make uninstall
    
    make PREFIX=/usr install


[Get the slackware package here](http://sourceforge.net/projects/usm)



=====================//======================
* all beyond is taken from: https://sourceforge.net/p/usm/wiki/Home/

USM (Unified Slackware Package Manager)
Description
USM is a unified slackware package manager that supports dependency resolution. It integrates various package repositories including slackware, slacky, ponce, salix and alien. It supports building packages from slackbuilds.org. It also includes a system wide dependency resolver.

It comes as a CLI/GUI hybrid which means if you run it from the menu you will use the Graphical User Interface. If you run it from a console you will use the Command Line Interface.

DOWNLOAD LATEST VERSION

Requirements/Dependencies
gtkdialog 0.8.3 >=

Table of contents
History
Usage
Usage explained
Config files
Known bugs
Todo list

History
Launched: 15th January 2014

USM came into being as an attempt to increase (if ever so slightly) the number of packages readily available for slackware and to offer some kind of dependency resolution, all in one tool.

This application is in it's infancy and is continually being developed. Suggestions and feedback are most welcome.


Usage
To use the GUI just open it from a menu. Be sure to update the databases before doing anything else.

For a usage example put a "?" after the option: usm -u ?

You may use either the single letter argument or full word.
For example the following have exactly the same meaning.

usm -u slackware
usm -update slackware
usm --update slackware
usm update slackware
-u [alien|salix|slackers|slackware|slacky|all|usm] Update databases.
-k <keyword> Keyword search
-d <package> Resolve dependencies
-s <package> Package search.
-s <library> Reverse library search.
-i <package> Package information.
-g <package> Download package.
-l <package> List packages.
-c <distro> Open repo changelog.
-b <package> Build package from source.
-h Show this help.
-S </path/to/folder> Set local storage.
Slackbuild options
          **usm sbo -l**
list all available categories in slackbuilds.
usm sbo -l multimedia
list all available packages in multimedia category.
usm sbo -b cueplayer
attempt to build cueplayer package from source.
usm sbo -i cueplayer
get information about a given package.
usm sbo -s cueplayer
search for a given package.


Usage explained
-u Update database
Used to download/update the database files that contain the package information for different distros. To check for updates to USM itself use: usm -u usm

-d Resolve dependencies
Resolve dependencies for a single package. You may use: usm -d /var/log/packages/my-package-x86_64-1 or give the path to an uninstalled slackware package on your storage device. If no path is given then USM will attempt to resolve all system dependencies. It will give you a report about what is missing, and the opportunity to download the packages.

-s Search for a package or library
Enter all or part of a package name to search the database for this package. If you enter a library name (E.g libsomething.so.1.2.3) then USM will attempt to return the package that the library belongs to.

-k Search by keyword
Searches for existing packages by keywords.
For example: *usm -k lossy compression"

-i Package information
This option returns the package name, size, install status and description of any packages found for the package you type.

-g Download package
Searches for and downloads the requested package. USM will attempt to resolve dependencies (and dependencies of dependencies) for the requested package.

-l List packages
If no argument is given it will list all installed packages. If an argument is given it will search the installed packages for word you type.

-c Open distro changelog
This will open the ChangeLog.txt file for a given repository. This is useful when you want to see what new packages were added to a repo.

-S Set local storage.
If -S is followed by a path to a directory on your computer then it will set the local storage to this path and all downloaded packages will land in the given directory.

END TAGS (To be used after all other arguments)

linksonly Show links only (end tag)
This will only show the links for your downloads. Useful if you prefer to use a download manager to download your packages.

noprompts Don't show prompts (end tag)
It will download your packages without asking you any questions.

nodeps No dependency resolution
Only download the chosen package.


Config files
/etc/usm/usm.conf
While most settings can be changed within the application, you may edit the config file directly. It is well commented and easy to understand.

/etc/usm/mirrors-distro.txt
This file contains the URL of the repository that will be used by USM. Please make sure ONLY ONE repository is uncommented in this file.


Known bugs
When USM opens a changelog file for a distro, it will attempt to find the system browser. If it finds one it will open the ChangeLog.txt file in the system browser and send the process to the background. This is producing an error in the terminal which occasionally hangs until killed via ctrl+c. This hanging process persists even after the browser is closed.


TODO list
View real time TODO list

Add 32bit support ## DONE
Add slackware patches section ## DONE
Add slackbuilds support ## DONE FOR CLI
Add check for non slackware compliant packages ## DONE
Add option to skip dependency checking ## DONE
Take a holiday
 
Last edit: brokenman 2014-05-30
