#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2012 Nexenta Systems, Inc.  All rights reserved.
#

#
# cmd/fs.d/fuse/dtrace/Makefile
#

PROG=	fuse.pc

include		$(SRC)/cmd/Makefile.cmd

ROOTLIBPKGCONF=  $(ROOTLIB)/pkgconfig
FILEMODE = 0444

all install: $(ROOTLIBPKGCONF)/$(PROG)

lint:

clean:

clobber:

$(ROOTLIBPKGCONF)/% : $(ROOTLIBPKGCONF) %
	$(INS.file)

$(ROOTLIBPKGCONF):
	$(INS.dir)

.KEEP_STATE:
