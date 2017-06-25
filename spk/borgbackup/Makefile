SPK_NAME = borgbackup
SPK_VERS = 1.1.0b6
SPK_REV = 1
SPK_ICON = src/borgbackup.png
BETA = 1

#UNSUPPORTED_ARCHS = $(PPC_ARCHES)

BUILD_DEPENDS = cross/python cross/setuptools cross/pip cross/wheel 
BUILD_DEPENDS += cross/$(SPK_NAME)

WHEELS = src/requirements.txt

MAINTAINER = jdeluyck
DESCRIPTION = Deduplicating archiver with compression and encryption.
DISPLAY_NAME = Borgbackup
CHANGELOG = "Initial commit"
HOMEPAGE = http://www.borgbackup.org
LICENSE = BSD-3

#INSTALLER_SCRIPT = src/installer.sh
#SSS_SCRIPT = src/dsm-control.sh
#FWPORTS = src/${SPK_NAME}.sc

INSTALL_PREFIX = /usr/local/$(SPK_NAME)

#BUSYBOX_CONFIG = usrmng daemon nice
#ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"

include ../../mk/spksrc.spk.mk

