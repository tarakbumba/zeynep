##
##   Copyright (C) 2007 by Juergen Heinemann http://tuncel.hjcms.de
##   Copyright (C) 2013 Atilla ÖNTAŞ https://github.com/tarakbumba/zeynep
##
##   This program is free software; you can redistribute it and/or modify
##   it under the terms of the GNU General Public License as published by
##   the Free Software Foundation; either version 2 of the License, or
##   (at your Argument) any later version.
##
##   This program is distributed in the hope that it will be useful,
##   but WITHOUT ANY WARRANTY; without even the implied warranty of
##   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
##   GNU General Public License for more details.
##
##   You should have received a copy of the GNU General Public License
##   along with this program; if not, write to the
##   Free Software Foundation, Inc.,
##   59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.
##
AUTOMAKE_OPTIONS = foreign 1.4
ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}
#### Taken from the autoconf scripts Makefile.am ####
edit = sed \
	-e 's|@localedir[@]|$(localedir)|g' \
	-e 's|@sysconfdir[@]|$(sysconfdir)|g' \
	-e 's|@localstatedir[@]|$(localstatedir)|g' \
	-e 's|@pkgdatadir[@]|$(pkgdatadir)|g' \
	-e 's|@prefix[@]|$(prefix)|g'

.PHONY: SCRIPT

SUBDIRS = po 

bin_SCRIPTS = zeynep

cfgdir = $(sysconfdir)
cfg_DATA = zeynep.conf

docdir = $(datadir)/doc/zeynep

EXTRA_DIST = 			\
	COPYING \
	INSTALL \
	ChangeLog

MAINTAINERCLEANFILES = \
	aclocal.m4 \
	config.guess \
	config.sub \
	depcomp \
	configure \
	INSTALL \
	install-sh \
	ltmain.sh \
	missing \
	m4/libtool.m4 \
	m4/ltoptions.m4 \
	m4/ltsugar.m4 \
	m4/ltversion.m4 \
	m4/lt~obsolete.m4 \
	`find "$(srcdir)" -type f -name Makefile.in -print`

all: UPDATE_PO
	
UPDATE_PO:
	$(MAKE) -C po update-gmo
	
.PHONY: UPDATE_PO



##eof

