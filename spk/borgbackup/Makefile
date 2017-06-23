SPK_NAME = borgbackup
SPK_VERS = 1.1.0b6
SPK_REV = 1
SPK_ICON = src/borgbackup.png
DSM_UI_DIR = app
BETA = 1

UNSUPPORTED_ARCHS = $(PPC_ARCHES)

BUILD_DEPENDS = cross/python cross/setuptools cross/pip cross/wheel 
BUILD_DEPENDS += cross/$(SPK_NAME)

WHEELS = src/requirements.txt

MAINTAINER = jdeluyck
DESCRIPTION = Deduplicating archiver with compression and encryption.
DISPLAY_NAME = Borgbackup
CHANGELOG = "Initial commit"
HOMEPAGE = http://www.borgbackup.org
LICENSE = BSD-3

INSTALLER_SCRIPT = src/installer.sh
SSS_SCRIPT = src/dsm-control.sh
FWPORTS = src/${SPK_NAME}.sc

INSTALL_PREFIX = /usr/local/$(SPK_NAME)

#POST_STRIP_TARGET = syncthing_extra_install

#BUSYBOX_CONFIG = usrmng daemon nice
#ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"

include ../../mk/spksrc.spk.mk

.PHONY: syncthing_extra_install
borgbackup_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 600 src/config.xml $(STAGING_DIR)/var/config.xml
	install -m 644 src/options.conf $(STAGING_DIR)/var/options.conf
	install -m 755 -d $(STAGING_DIR)/app
	install -m 644 src/app/config $(STAGING_DIR)/app/config
