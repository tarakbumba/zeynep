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

Overview
------------
As you may see, zeynep is not ready for production. I intend to create three bash scripts:
- zeynep-tarball-creator : Chroot environment generator and archiver (DONE)
- zeynep-package-builder : Package builder and does other things that i think (NOT DONE)
- zeynep : Master of the Universe. :) One bash script that combines above two.

Usage
------------
zeynep [-g][options] [arguments] [-s] [srpm]

 * -m        - Mageia version which rpms build for. Default: Cauldron
 * -g        - Generate a chroot tarball which is used for building rpm
 * -s        - Exact path/name of the srpm file. E.g. /home/user/foo-1.0-1.mga4.src.rpm
 * -D        - Temporary directory for chroot environment. Can be used with '-g' option. Default: /tmp
 * -d        - URL to retrive a set of media from a distribution.Uses 'urpmi.addmedia --distrib'. Default: MIRRORLIST
 * -c        - RPM cache directory which will be used for save time/bandwith. Default: Disabled
 * -M        - URL to retrive packages from. E.g. 'www.someurl.org/pub/mageia/4/media/i586'. Default: Disabled
 * -n        - Do not ignore specified medias in quote marks. E.g "Nonfree Tainted Backports"). Default: Disabled
 * -U        - Additional urpmi options to be used either in tarball creation or package building.
 * -u        - Upload directory for created rpm packages. Default: Use path which srpm resides
 * -a        - Architecture of Mageia version. This could be i586 on a 32 machine or i586, x86-64 or both of them for a 64bit machine. Default: Current machine arch
 * -t        - Path of where chroot tarballs are/should reside. This option is mandatory.
 * -C        - Use 'rpm-tidy' utility to clean older rpms in cache directory. Default: Disabled
 * -T        - Use 'rpm-tidy' utility to clean older rpms in rpm upload directory. Default: Disabled
 * -N        - Do not clean chroot environment upon exit. Default: Disabled
 * -l        - Upload compiled rpms into srpm's directory. Default: Disabled unless you did not use '-u' option
 * -S        - Sign rpm packages via rpm-sign utility. Default: Disabled
 * -G        - Generate hdlists for compiled rpms upon exit. Default: Disabled
 * -v        - Be verbose. Default: Disabled
 * -V        - Be very verbose. Default: Disabled
*  -h        - Display help
 
Examples:

* Creating a chroot tarball for Mageia 4 with cache for a x86_64 system:

   zeynep -g -m 4 -a x86-64 -c $HOME/rpm/cache/x86_64

* Creating signed rpms from a srpm for Mageia 4 with cache for a x86_64 system using a distrib mirror and creating genhdlist without upload dir: (Created rpms will reside in $HOME/RPMS/x86_64 directory)

   zeynep -TG -m 4 -t "$HOME/rpm/chroot-tarballs" -d http://ftp.linux.org.tr/mageia/distrib -a x86_64 -s $HOME/foo-1.0-1.mga4.src.rpm
    
* Creating signed rpms from a srpm for Mageia 4 with cache for a x86_64 system using a distrib mirror and creating genhdlist with upload dir:

   zeynep -TG -m 4 -t "$HOME/rpm/chroot-tarballs" -d http://ftp.linux.org.tr/mageia/distrib -a x86_64 -u $HOME/rpms -s $HOME/foo-1.0-1.mga4.src.rpm


Authors:
-------------
Atilla ÖNTAŞ <tarakbumba at gmail dot com >





