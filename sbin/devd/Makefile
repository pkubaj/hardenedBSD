# $FreeBSD$

.include <src.opts.mk>

PACKAGE=runtime
PROG_CXX=devd
SRCS=	devd.cc token.l parse.y y.tab.h
MAN=	devd.8 devd.conf.5

WARNS?=	3

.if ${MK_DEVD_PIE} == "no"
NO_SHARED?=YES
.endif

LIBADD=	l util

YFLAGS+=-v
CFLAGS+=-I. -I${.CURDIR}

CLEANFILES= y.output

HAS_TESTS=
SUBDIR.${MK_TESTS}+= tests

.include <bsd.prog.mk>
