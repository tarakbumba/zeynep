### - Update gettext catalogs and Changelog (HEAD -> master)
>Mon, 7 Dec 2015 00:36:11 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Fix minor bug with urpmi.addmedia options (origin/master, origin/HEAD)
>Mon, 30 Nov 2015 23:08:59 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- urpmi.addmedia doesn't have an "--auto" option. Remove "--auto".
  Fixes #12
- As usual update gettext catalogs and Changelog



### Fix a crashing bug when no tarball is existed or used (#10)
>Mon, 30 Nov 2015 21:42:24 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- Zeynep should not try to unmount /var/cache/rpms when cache option isn't used
- Add check for user input in French ("Oui)
- Update gettext catalogs and Changelog



### Fix a minor bug in unmount_necessary_dirs function
>Sat, 28 Nov 2015 19:45:56 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- /dev/shm used for building some packages like webkit/chromium browser.
 Thus we need to explicitly ensure that /dev/shm is unmounted upon exit.
 (Fixes #9. Thanks to Alexander Khryukin)

- As usual gettext catalogs and Changelog are updated



### Fix a regression in care_medias function user input
>Sat, 28 Nov 2015 00:41:19 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- Fix regression introduced by commit 8c7f35fe5479a24278ad21a54033337db359cadd
- As usual update gettext catalogs and Changelog



### Adjust rpmmacros for Mageia 6 macro changes for package suffix
>Sat, 28 Nov 2015 00:24:08 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- Mageia 6 introduces a new approach for package naming scheme (.mga part.)
  Beginnign with Mageia 6 %distsuffix macro is ignored and %dist macro is
  introduced. We now check for changes and modify rpmmacro file accordingly.

- Remove unneeded copying /etc/skel/.rpmmacros to home dir introduced by
  commit 1df0aaa3feee48b4e23ba87d640ea6b11c206e3c

- As usual update gettext catalogs and Changelog



### Fix a bug in care_medias function
>Sat, 28 Nov 2015 00:08:52 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- When a media can not be enabled, user input was ignored and script exits.
  This commit solves this bug and adds French support for user input.

- As usual gettext catalogs and Changlog are updated.



### Fix minor bug for enabled media types function
>Sun, 22 Nov 2015 01:11:47 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

* Our "care_medias" function, which is responsible for enabling media
repos (non-free, tainted,*-testing etc.) was unsuccesfull to detect
if relevant option is used when running zeynep. Now it corretcly detects
this and runs code block if "-n" option is used with zeynep.



### Fix some messages and update gettext catalogs
>Sat, 21 Nov 2015 02:12:26 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

* For easy translation some MAKEFILE variables removed from strings.
* Updated Turkish translation catalog also.



### *  Fix a bug of log file path
>Sat, 21 Nov 2015 01:56:40 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- Zeynep now ensures that if a srpm is given and logs into srpm path;
otherwise it puts logs into /tmp directory.
- Zeynep now uses timestamp for log file name and doesn't delete old
logs.



### * Fix minor bug and add new Changelog
>Sat, 21 Nov 2015 01:46:04 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

- Fix displayed message when urpmi media installation fails
- Add a new format Changelog file



### Fix minor bugs: * Fix rpmmacros file copy and usage in rpm building. * Fix an issue about displayed message when installation media fails.
>Sat, 21 Nov 2015 01:40:00 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update Readme.md
>Mon, 16 Nov 2015 23:04:08 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update translations
>Mon, 16 Nov 2015 22:33:52 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Add ability to pass arguments to rpmbuild via "-b" switch
>Mon, 16 Nov 2015 22:18:37 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Don't use $XDG_CONFIG_HOME for ~/.config, some setups don't set that variable
>Mon, 16 Nov 2015 22:07:47 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### * Create log file in srpm path not in /tmp
>Mon, 16 Nov 2015 22:03:29 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Tidy rpms even they are different archs Before this commit, rpm-tidy usage would gave error if rpms directory has different arch type rpms. Now it correctly handles obsolete rpms which have same arch.
>Tue, 12 May 2015 23:49:33 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update changelog and translations
>Mon, 13 Apr 2015 01:07:03 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Fix postbuild_functions
>Mon, 13 Apr 2015 00:46:43 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

We had used postbuild_functions function just after building phase. But, users
may want to do extra stuff *after* rpms upload to upload path.



### Fix postbuild_functions
>Mon, 13 Apr 2015 00:46:43 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

We had used postbuild_functions function just after building phase. But, users
may want to do extra stuff *after* rpms upload to upload path.



### Silence rpm-tidy detection
>Mon, 13 Apr 2015 00:40:47 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

Redirect "which" command output to /dev/null in order to hide unnecessary
verbosity



### Silence urpmi detection
>Mon, 13 Apr 2015 00:36:37 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

Redirect "which" command output to /dev/null in order to hide unnecessary
verbosity.



### Fix logging and trapping
>Mon, 13 Apr 2015 00:33:38 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

Redirecting stdout and stderr to tee directly somehow breaks traps. The only
way i have found is using mkfifo...



### Fix unnecessary rpm-tidy verbosity and be more accurate
>Mon, 13 Apr 2015 00:28:18 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

In tidy_rpms function, detecting different arch rpms in same directory was done
by "ls" command usage. But this was not accurate. Instead we' re now using "test"
and "find" command with extra arguments. Basically, test command evaluates "find"
commands findings are none or not. Find is executed only in basedir and doesn't
search subdirs thanks to "-maxdepth 0". It also prints its findings (test evaluates
this).

We also now succesfully hide find's search results from console and log file.



### Remove newline sequences from gettext dialogs and update gettext catalogs
>Sun, 29 Mar 2015 23:34:38 +0300

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Add src.rpm existance check - Altough zeynep tries to detect given file's type and exists if it's not a srpm file; zeynep should also check if given srpm file exists. It should exit if srpm file doesn't exist at the very beginning.
>Mon, 23 Mar 2015 01:02:15 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update translation catalogs
>Tue, 3 Mar 2015 01:05:54 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

Update changelog file too...



### Update "-n" option instructions
>Tue, 3 Mar 2015 00:41:33 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

This patch updates instructions for "-n" option.



### Fix media sources
>Tue, 3 Mar 2015 00:22:47 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)

This commit fixes media sources (Nonfree, Tainted etc.) enabling.



### Fix updating packages in chroot with defined urpmi options (fixes also cache usage)
>Sun, 1 Mar 2015 02:02:39 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update specfile for source line and github api
>Fri, 27 Feb 2015 23:11:37 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update translations
>Sat, 24 Jan 2015 12:41:51 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update gettext catalogs
>Sat, 24 Jan 2015 12:10:30 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Fixed some bugs in zeynep.in
>Sat, 24 Jan 2015 01:43:17 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

- Change from $MIRRORLIST to http://mirrors.mageia.org/api/mageia.${mga_version}.${arch}.list
  Before this change; zeynep always got i586 mirrorlist when 'both' argument passed to '-a' option.

- Fix usage of $mga_version and $arch variables at commandline
  If user types paths or URLs for options like cache or media using $mga_arch or $arch, zeynep
  couldn't fill these variables thus paths or URLs were failing. This commit fixes this issue.

- Fix building with 'both' argument usage for '-a' option
  If user tries to build packages or tarballs for both archs (i586/x86_64) using 'both' argument;
  zeynep was failing to perform tasks with x86_64 arch. There were leftover variable assignements
  from i586 task. This commit hopefully fix this issue.

- Update ChangeLog



### Update Changelog
>Sat, 24 Jan 2015 01:31:38 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Bug fixing in zeynep.in (Issue #4) - Implement /etc/skel/.rpmmacros search and setting into control_rpmmacros function. This commit should fix issue#4
>Sat, 24 Jan 2015 01:29:02 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Bug fixing in zeynep.in
>Sat, 24 Jan 2015 01:20:42 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

- Fix a bug that prints all rpm-tidy functions output to screen



### Add git.mk to po/Makefile.am
>Fri, 23 Jan 2015 20:30:40 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Update zeynep.conf.in
>Thu, 22 Jan 2015 17:03:18 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Add tempdir and media url options in configuration
Explain which options unneeded if it resides in configuration


### Update zeynep.in
>Thu, 22 Jan 2015 13:31:46 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Add "R" option to getopts line.


### Update README.md
>Thu, 22 Jan 2015 13:24:46 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

- Added -R option explanation


### Update zeynep.in
>Thu, 22 Jan 2015 13:22:42 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

- Add forgotten option for rpmmacros usage (#4)


### Update README.md
>Wed, 21 Jan 2015 16:04:51 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Fix github markup for known limitations part.


### Update README.md
>Wed, 21 Jan 2015 16:03:34 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Add getopts limitations into known issues part


### Update README.md
>Wed, 21 Jan 2015 15:53:11 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Added how to configure sudoers file.
Tidy up codes for github markup.


### - Update translation catalogs
>Wed, 21 Jan 2015 01:48:43 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Add option to not use chroot-tarball
>Wed, 21 Jan 2015 01:35:04 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Fix typo in searching installed utilities - Add check for root run (tag: 1.0.3)
>Tue, 20 Jan 2015 23:58:19 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Update README.md
>Mon, 19 Jan 2015 16:13:42 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Fix translation catalogs. (tag: 1.0.2)
>Mon, 19 Jan 2015 03:17:09 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Update translation catalogs
>Mon, 19 Jan 2015 03:14:24 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Be a bit verbose to screen in run_command functions. - Silent rpm-tidy checks with 'ls' command. - Tidy up error messages.
>Mon, 19 Jan 2015 03:02:39 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




###  - Fix command run functionsto run commands properly (#2) - Ensure that user supplied paths do not contain '/' at the end of path
>Mon, 19 Jan 2015 02:04:11 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Fix bug with rpm upload function - Add debug of running commands to log file - More messages for user
>Sun, 18 Jan 2015 02:37:12 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Create user in chroot with same id/name of the zeynep user
>Sun, 18 Jan 2015 01:02:30 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Update README.md
>Sat, 17 Jan 2015 02:31:27 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Update pot catalogs and translations (tag: 1.0.1)
>Sat, 17 Jan 2015 02:12:58 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Fix source line in rpm specfile example
>Sat, 17 Jan 2015 01:40:41 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Workaround rpm-tidy bug regarding to rpm's arch in comparison
>Sat, 17 Jan 2015 01:37:25 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - For tarball creation: Add locale packages installation same as host systems to add locales support in chroot
>Wed, 14 Jan 2015 22:40:36 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Fix typo in tidy_rpms function
>Wed, 14 Jan 2015 22:24:29 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Add rpm specfile
>Wed, 14 Jan 2015 22:05:58 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Fix installation dir in README.md (tag: 1.0.0)
>Wed, 14 Jan 2015 20:11:46 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Updated translation catalogs - Fix a message in rpm list function
>Wed, 14 Jan 2015 20:10:08 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Update README.md
>Wed, 14 Jan 2015 14:34:54 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Add files from previous commit
>Wed, 14 Jan 2015 02:40:55 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Add autotools files - Empty src dir and move zeynep script to top level dir as zeynep.in - Add external utilities check to zeynep.in
>Wed, 14 Jan 2015 02:39:08 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Fix bug when arch=both used - Add sourcing configurations - Add an option to use default 'MIRRORLIST' urpmi source - Add more informational messages
>Tue, 13 Jan 2015 00:56:01 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Add config file sourcing - Update config file skeleton and README - Add option to allow user determined packages installed when tarballs are created - Fix Mageia version and arch when urpmi distrib medium is added - Add check statement if user specified Mageia version, if not default to cauldron
>Sun, 11 Jan 2015 22:26:31 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Update README.md
>Sun, 11 Jan 2015 15:38:16 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Add bug reporting link


### Update README.md
>Sun, 11 Jan 2015 15:35:30 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Fix help option display


### Update README.md
>Sun, 11 Jan 2015 15:34:47 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)

Fix wrong wrapping of zeynep options


### Add a config file skeleton
>Sun, 11 Jan 2015 12:38:42 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### - Fix noclean option usage - Fix rpm-tidy to actually tidy rpms - Add more messages
>Sun, 11 Jan 2015 04:41:11 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Remove noarch package checks - Add updating rpms in chroot environment before package building.
>Sun, 11 Jan 2015 02:45:23 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### First working script
>Sat, 10 Jan 2015 23:52:51 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Remove unused tidy_log_file and trap_function functions
>Fri, 2 Jan 2015 22:53:41 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




###  Add gitignore file
>Thu, 1 Jan 2015 23:35:57 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




###  Add first and incomplete zeynep script
>Thu, 1 Jan 2015 23:33:58 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### - Add a simple readme
>Wed, 24 Dec 2014 02:31:59 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




### Initial commit with chroot-builder script
>Tue, 23 Dec 2014 20:41:03 +0200

>Author: tarakbumba (tarakbumba@gmail.com)

>Commiter: tarakbumba (tarakbumba@gmail.com)




### Initial commit
>Tue, 23 Dec 2014 20:37:23 +0200

>Author: Atilla ÖNTAŞ (tarakbumba@gmail.com)

>Commiter: Atilla ÖNTAŞ (tarakbumba@gmail.com)




