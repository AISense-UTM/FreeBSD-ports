# Created by: ijliao
# $FreeBSD$

PORTNAME=	rpy2
PORTVERSION=	2.7.8
PORTREVISION=	5
CATEGORIES=	math
MASTER_SITES=	CHEESESHOP

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Python interface to the R Programming Language

LICENSE=	GPLv2+

BUILD_DEPENDS=	${PYNUMPY} \
		R:math/R
RUN_DEPENDS=	${PYNUMPY} \
		R:math/R

USES=		fortran python readline
USE_PYTHON=	distutils autoplist
LDFLAGS+=	-Wl,--as-needed

pre-configure:
	@(if [ ! -e ${LOCALBASE}/lib/R/lib/libR.so ] ; then \
	${ECHO_MSG} "==> ${PKGNAME} requires math/R to be built with the" ; \
	${ECHO_MSG} "==> LIBR option enabled." ; \
	exit 1; fi)

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/rpy2/rinterface/*.so

.include <bsd.port.mk>
