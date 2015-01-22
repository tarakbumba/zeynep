dnl
dnl   Copyright (C) 2013 Atilla ÖNTAŞ https://github.com/tarakbumba/zeynep
dnl
dnl   This program is free software; you can redistribute it and/or modify
dnl   it under the terms of the GNU General Public License as published by
dnl   the Free Software Foundation; either version 2 of the License, or
dnl   (at your Argument) any later version.
dnl
dnl   This program is distributed in the hope that it will be useful,
dnl   but WITHOUT ANY WARRANTY; without even the implied warranty of
dnl   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
dnl   GNU General Public License for more details.
dnl
dnl   You should have received a copy of the GNU General Public License
dnl   along with this program; if not, write to the
dnl   Free Software Foundation, Inc.,
dnl   59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.
dnl

AC_PREREQ([2.69])

AC_INIT([zeynep], [1.0.4], [https://github.com/tarakbumba/zeynep/issues], [https://github.com/tarakbumba/zeynep])

AM_INIT_AUTOMAKE([1.9 tar-ustar dist-xz foreign no-dist-gzip])

AC_CONFIG_MACRO_DIR([m4])
AC_PREFIX_DEFAULT(/usr)

test "$sysconfdir" = '${prefix}/etc' && sysconfdir=/etc
AC_SUBST(SYSCONFDIR,${sysconfdir})

dnl -----------------------------------------------
dnl Package name and version number (user defined)
dnl -----------------------------------------------
PACKAGE_AUTHOR="Atilla ÖNTAŞ (tarakbumba)"
AC_SUBST([PACKAGE_AUTHOR])

PACKAGE_SUMMARY="A rpm build utility with lots of features in clean chroot environment for Mageia GNU/Linux Distribution"
AC_SUBST(PACKAGE_SUMMARY)

dnl -----------------------------------------------
dnl Error Handler
dnl -----------------------------------------------
AC_DEFUN([AC_MISSING],AC_MSG_ERROR(["can not find $1 application"]))

dnl -----------------------------------------------
dnl make set requires
dnl -----------------------------------------------
AC_PROG_AWK
AC_PROG_SED
AC_PROG_MAKE_SET
AC_PROG_MKDIR_P
AC_PROG_LN_S
AC_PROG_INSTALL


dnl -----------------------------------------------
dnl gettext and intltool
dnl -----------------------------------------------
AC_CHECK_PROG(HAVE_GETTEXT, gettextize, yes, no)
AC_PATH_PROG(GETTEXT, gettextize, no)
if test "x$HAVE_GETTEXT" = "xno"; then
		AC_MSG_ERROR(you need to have gettext installed !)
fi dnl
AC_SUBST(GETTEXT)

AC_CHECK_PROG(HAVE_INTLTOOL, intltoolize, yes, no)
AC_PATH_PROG(INTLTOOL, intltoolize, no)
if test "x$HAVE_INTLTOOL" = "xno"; then
		AC_MSG_WARN(you need to have intltool installed !)
fi dnl
AC_SUBST(INTLTOOL)

AC_CHECK_PROGS([ENVSUBST],
  [envsubst],
  [AC_MSG_ERROR(["envsubst from gettext not found"])]
) dnl
AC_SUBST(ENVSUBST)

AC_SUBST(TEXTDOMAIN,"$PACKAGE_NAME")
AM_PO_SUBDIRS

dnl -----------------------------------------------
dnl Install Directories
dnl -----------------------------------------------
AC_PREFIX_PROGRAM([$GETTEXT])

dnl -----------------------------------------------
dnl Generates Makefile's, configuration files and scripts
dnl -----------------------------------------------
AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([zeynep])
AC_CONFIG_FILES([zeynep.conf])
AC_CONFIG_FILES([po/Makefile],[AM_POSTPROCESS_PO_MAKEFILE])
AC_OUTPUT

dnl ---------------------------------------------------------------------------
dnl - Show summary
dnl ---------------------------------------------------------------------------

echo "
---------------------- summary -------------------------

          bindir: ${prefix}/bin
         locales: ${prefix}/share/locale
   configuration: ${sysconfdir}/zeynep.conf
---------------------------------------------------------

Now type 'make' then 'make install' as root or 'make DESTDIR=/tmp install'

"

dnl -----------------------------------------------
