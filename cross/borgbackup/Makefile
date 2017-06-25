PKG_NAME = borgbackup
SHORT_NAME = borg
PKG_VERS = 1.1.0b6
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/$(PKG_NAME)/$(SHORT_NAME)/archive
PKG_DIR = $(SHORT_NAME)-$(PKG_VERS)

DEPENDS = cross/fuse cross/python3

HOMEPAGE = http://www.borgbackup.org/
COMMENT  = Deduplicating archiver with compression and encryption
LICENSE  = BSD-3

include ../../mk/spksrc.python-wheel.mk

