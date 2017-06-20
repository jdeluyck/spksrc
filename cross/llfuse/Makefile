PKG_NAME = python-llfuse
PKG_VERS = 1.2
PKG_EXT = tar.gz
PKG_DIST_NAME = release-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/$(PKG_NAME)/$(PKG_NAME)/archive
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS = cross/setuptools

HOMEPAGE = https://pypi.python.org/pypi/llfuse
COMMENT  = Python bydings for the low-level FUSE API
LICENSE  = LGPL

include ../../mk/spksrc.python-module.mk
