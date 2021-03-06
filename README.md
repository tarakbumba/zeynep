zeynep
======

RPM packages build tool in a clean Mageia chroot environment for Mageia Linux distribution

Zeynep is a bash script which generates a chroot environment, installs basesystem, compresses it
into a tar.xz archive for future uses. It can creates a chroot environment using its own generated tar.xz
archive; copies source rpm package into chroot; installs build dependencies and creates rpm packages.

I tried to use "iurt" but could not find a guide enough to understand. I tried "aum" (perl version)
and it was very useful. Unfortunately i needed some futures that aum does not have:

- Using an rpm cache to save bandwith but not download an entire repository
- Using configuration files that makes me less type on the screen
- Using some mechanism that automates my needs after package building, like generating
synthesis lists etc.
- Aum and aum++ are written in Perl and C++ respectively and i know neither of those. It was hard for me to
add futures that i need.

So, zeynep born. 

Usage
------------
* First things first; never try to run zeynep as root! It will use "sudo" when required. If you don't want to type your sudo password every time needed; then add zeynep to your /etc/sudoers file; but this may also RISKY! See below how to configure /etc/sudoers.


* zeynep [-g][options] [arguments] [-s] [srpm]

 * -m        - Mageia version which rpms build for. Default: Cauldron
 * -g        - Generate a chroot tarball which is used for building rpm
 * -Z        - Do not use a chroot tarball. Instead create chroot environment from strach and build packages in there.
 * -s        - Exact path/name of the srpm file. E.g. /home/user/foo-1.0-1.mga4.src.rpm
 * -D        - Temporary directory for chroot environment. Can be used with '-g' option. Default: /tmp
 * -d        - URL to retrive a set of media from a distribution.Uses 'urpmi.addmedia --distrib'. Default: MIRRORLIST
 * -z        - Force zeynep to not use given distrib media with -d switch/or from config file and default to MIRRORLIST
 * -c        - RPM cache directory which will be used for save time/bandwith. Default: Disabled
 * -M        - URL to retrive packages from. E.g. 'www.someurl.org/pub/mageia/4/media/i586'. Default: Disabled
 * -p        - Packages names to be installed in chroot. This option must be used with '-g' option and each package must be seperated by a space in quotes. E.g. 'locales-tr wget' Default: Disabled
 * -n        - Do not ignore specified medias in quote marks. E.g "Nonfree Tainted Backports". Default: Disabled
 * -U        - Additional urpmi options to be used either in tarball creation or package building.
 * -u        - Upload directory for created rpm packages. Default: Use path which srpm resides
 * -a        - Architecture of Mageia version. This could be i586 on a 32 machine or i586, x86-64 or both of them for a 64bit machine. Default: Current machine arch
 * -t        - Path of where chroot tarballs are/should reside. If not set by user, zeynep will create a chroot and build packages in there.
 * -C        - Use 'rpm-tidy' utility to clean older rpms in cache directory. Default: Disabled
 * -T        - Use 'rpm-tidy' utility to clean older rpms in rpm upload directory. Default: Disabled
 * -N        - Do not clean chroot environment upon exit. Default: Disabled
 * -l        - Upload compiled rpms into srpm's directory. Default: Disabled unless you did not use '-u' option
 * -S        - Sign rpm packages via rpm-sign utility. Default: Disabled
 * -b        - Commandline arguments to be passed on rpmbuild. Use the arguments in double quotes
 * -G        - Generate hdlists for compiled rpms upon exit. Default: Disabled
 * -R        - Add rpmmacros file from user home dir (~/.rpmmacros). Default: Disabled
 * -P         - Upload re-created srpms into user defined path. Default: Disabled
 * -v         - Be verbose. Default: Disabled
 * -V        - Be very verbose. Default: Disabled
 * -h        - Display help
 
Examples:

* Creating a chroot tarball for Mageia 4 with cache for a x86_64 system with user defined packages also installed:

		zeynep -g -m 4 -a x86-64 -c $HOME/rpm/cache/x86_64 -p "wget vim task-kde"

* Creating signed rpms from a srpm for Mageia 4 with cache for a x86_64 system using a distrib mirror and creating genhdlist without upload dir: (Created rpms will reside in $HOME/RPMS/x86_64 directory)

		zeynep -SG -m 4 -t "$HOME/rpm/chroot-tarballs" -d http://ftp.linux.org.tr/mageia/distrib -a x86_64 -s $HOME/foo-1.0-1.mga4.src.rpm
    
* Creating signed rpms from a srpm for Mageia 4 with cache for a x86_64 system using a distrib mirror and creating genhdlist with upload dir:

		zeynep -SG -m 4 -t "$HOME/rpm/chroot-tarballs" -d http://ftp.linux.org.tr/mageia/distrib -a x86_64 -u $HOME/rpms -s $HOME/foo-1.0-1.mga4.src.rpm
   
* Building x86_64 arch rpm packages for Mageia 4 without pre-created tarball usage:

		zeynep -ZG -m 4 -d http://ftp.linux.org.tr/mageia/distrib -a x86_64 -s $HOME/foo-1.0-1.mga4.src.rpm

Installation:
--------------
You should have at least autoconf and gettext-devel packages installed to build and install zeynep. Normally you should run 

		./autogen.sh
 
		./configure
 
		make
 
and as root

		make install
 
Without any option specified zeynep will install in /usr directory. Please refer to the INSTALL file for installation steps and options.

Runtime Dependencies:
---------------------
Zeynep needs to rpm, urpmi, rpmbuild, sed and sudo be install to run. For localization support you should have gettext package installed. Also rpm-tidy and rpm-sign should be installed to clean older rpms and rpm signing features.

Configuration of /etc/sudoers (optional)
---------------------
This may be harmful for your setup and YOU'VE BEEN WARNED!

You can configure your /etc/sudoers file in a way that you won't need to type your sudo password everytime needed.
Add below lines at the end of your /etc/sudoers file. Note that you should use "visudo" command to do this:

		your_username ALL=(root) NOPASSWD: /whare/zeynep_is_installed/zeynep


Known Limitations:
--------------------
* Due to "getopts" limitations, if you type an argument required option before non argument required option zeynep will likely to fail. For example:

		zeynep -mZ 4 -s foo.src.rpm

You should notice that "Z" option follows "-m" option which requires an argument which is "4" here. Getopts parse these in a way that "Z" becomes argument for "-m" and this will result as mageia_version="Z" and of course zeynep will fail. So, do not use options like that. Altough this should work:

		zeynep -Zm 4 -s foo.src.rpm


Authors:
-------------
Atilla ÖNTAŞ <tarakbumba at gmail dot com >

Bugs:
-------------
Please report any bugs you've found to https://github.com/tarakbumba/zeynep/issues/new





