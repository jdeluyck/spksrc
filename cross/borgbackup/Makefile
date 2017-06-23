PKG_NAME = borgbackup
SHORT_NAME = borg
PKG_VERS = 1.1.0b6
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/$(PKG_NAME)/$(SHORT_NAME)/archive
PKG_DIR = $(PKG_NAME)

DEPENDS = cross/fuse cross/python

HOMEPAGE = http://www.borgbackup.org/
COMMENT  = Deduplicating archiver with compression and encryption
LICENSE  = BSD-3

CONFIGURE_TARGET = nope
COMPILE_TARGET = myComp
INSTALL_TARGET = myInstall

#GOOS = linux
#CGO_ENABLED=0

# set this to 1 to create static linked binaries
STATIC_BINARIES = 0

# Define SYNCTHING_ARCH as per Syncthing standards
ifeq ($(findstring $(ARCH),88f5281 88f6281 alpine armada370 armada375 armada38x armadaxp comcerto2k monaco),$(ARCH))
SYNCTHING_ARCH = arm
ENV += GOARM=5
endif
ifeq ($(findstring $(ARCH),evansport),$(ARCH))
SYNCTHING_ARCH = 386
endif
ifeq ($(findstring $(ARCH),avoton braswell bromolow cedarview x86 x64),$(ARCH))
SYNCTHING_ARCH = amd64
endif
ifeq ($(SYNCTHING_ARCH),)
$(error Unsupported ARCH $(ARCH))
endif

BORGBACKUP_DIR = $(WORK_DIR)/src/github.com/$(PKG_NAME)/$(SHORT_NAME)-$(PKG_VERS)
EXTRACT_PATH = $(WORK_DIR)/src/github.com/$(PKG_NAME)
BORGBACKUP_BIN = $(WORK_DIR)/src/github.com/$(PKG_NAME)/$(PKG_NAME)/syncthing

include ../../mk/spksrc.python-wheel.mk

# use workdir as gopath
#ENV += GOPATH=$(WORK_DIR)
#ENV += CGO_ENABLED=$(CGO_ENABLED)
#ENV += PATH=$(WORK_DIR)/../../../native/go/work-native/go/bin/:$$PATH

#CONF_ARGS = -goos=$(GOOS) -goarch=$(SYNCTHING_ARCH) -version=v$(PKG_VERS)

ifeq ($(strip $(STATIC_BINARIES)),1)
CONF_ARGS += -no-upgrade
endif

myComp:
	cd $(BORGBACKUP_DIR) && env $(ENV) go run build.go $(CONF_ARGS) build

myInstall:
	mkdir -p $(STAGING_INSTALL_PREFIX)/bin
	install -m 755 $(BORGBACKUP_BIN) $(STAGING_INSTALL_PREFIX)/bin/
