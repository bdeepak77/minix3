# Makefile for the mmc driver.
PROG=	mmc
SRCS=	mmcblk.c mmchost_dummy.c mmclog.h sdhcreg.h sdmmcreg.h


.if ${MACHINE_ARCH} == "earm"
SRCS += mmchost_mmchs.c 
.endif


DPADD+=	${LIBBLOCKDRIVER} ${LIBSYS}
LDADD+=	-lblockdriver -lsys
CLEANFILES+=.depend mmcblk.d

#
# This is a system driver.
CPPFLAGS+= -D_SYSTEM=1

MAN=

BINDIR?= /usr/sbin

.include <minix.service.mk>
