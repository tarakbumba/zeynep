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



Any toughts?

Atilla ÖNTAŞ <tarakbumba at gmail dot com >





