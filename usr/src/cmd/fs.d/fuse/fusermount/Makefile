#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
#
# Copyright 2010 Sun Microsystems, Inc.  All rights reserved.
# Use is subject to license terms.
#

#
# cmd/fs.d/fuse/fusermount/Makefile
#

FSTYPE=		fusefs
LIBPROG=	fusermount
ROOTFS_PROG=	$(LIBPROG)

include		../../Makefile.fstype

OBJS=	$(LIBPROG).o mount_util.o
SRCS=	$(LIBPROG).c
POFILE=	$(LIBPROG).po

$(ROOTLIBFSTYPE)/mount := FILEMODE= 04555

CFLAGS += $(CCVERBOSE)
C99MODE= $(C99_ENABLE)

LDLIBS += -lxnet

CPPFLAGS += \
	-I$(SRC)/lib/libfuse/include \
	-I$(SRC)/lib/libfuse/common \
	-D__SOLARIS__ \
	-D_XOPEN_SOURCE=600 \
	-D__EXTENSIONS__ \
	-D_FILE_OFFSET_BITS=64

.KEEP_STATE:

all:	$(ROOTFS_PROG)

$(LIBPROG):	$(OBJS)
	$(LINK.c) -o $@ $(OBJS) $(LDLIBS)
	$(POST_PROCESS)

catalog:	$(POFILE)

install:	$(ROOTLIBFSTYPEPROG)

lint:	lint_SRCS

clean:     
	$(RM) $(OBJS) $(POFILE)

mount_util.o : $(SRC)/lib/libfuse/common/mount_util.c
	$(COMPILE.c) $(OUTPUT_OPTION) \
	  $(SRC)/lib/libfuse/common/mount_util.c $(CTFCONVERT_HOOK)
	$(POST_PROCESS_O)
