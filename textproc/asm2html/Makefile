# Created by: Ben Haga <tuxsuximus@hotmail.com>
# $FreeBSD$

PORTNAME=	asm2html
PORTVERSION=	1.7
CATEGORIES=	textproc
MASTER_SITES=	http://bsdforge.com/projects/source/textproc/asm2html/

MAINTAINER=	portmaster@bsdforge.com
COMMENT=	Converts NASM syntax assembly code to HTML code

LICENSE=	BSD3CLAUSE

USES=		tar:xz
HAS_CONFIGURE=	yes
CONFIGURE_ARGS+=--prefix=${PREFIX}
MAKE_ARGS+=	CC=${CC}

PLIST_FILES=	bin/asm2html man/man1/asm2html.1.gz

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/asm2html ${STAGEDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/man/asm2html.1 \
		${STAGEDIR}${MANPREFIX}/man/man1

.include <bsd.port.mk>
