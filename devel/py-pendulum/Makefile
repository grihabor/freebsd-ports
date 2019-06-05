# $FreeBSD$

PORTNAME=	pendulum
PORTVERSION=	2.0.4
PORTREVISION=	3
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	garga@FreeBSD.org
COMMENT=	Python package to ease datetimes manipulation

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}dateutil>=2.6:devel/py-dateutil@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytzdata>=2018.3:devel/py-pytzdata@${PY_FLAVOR}
py27_RUN_DEPENDS= ${PYTHON_PKGNAMEPREFIX}typing>=3.6:devel/py-typing@${PY_FLAVOR}

USES=		python
USE_PYTHON=	distutils
py36_PLIST=	${.CURDIR}/pkg-plist-py3

HELPERS_SO=	${STAGEDIR}${PYTHON_SITELIBDIR}/pendulum/_extensions/_helpers.so
ISO8601_SO=	${STAGEDIR}${PYTHON_SITELIBDIR}/pendulum/parsing/_iso8601.so

post-install:
	@${SH} -c "[ -f ${HELPERS_SO} ] && ${STRIP_CMD} ${HELPERS_SO} || true"
	@${SH} -c "[ -f ${ISO8601_SO} ] && ${STRIP_CMD} ${ISO8601_SO} || true"

.include <bsd.port.mk>
