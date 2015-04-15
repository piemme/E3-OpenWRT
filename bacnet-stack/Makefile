#
# Copyright (C) 2015 Gualtiero Saderis (gualtiero.saderis@gmail.com)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bacnet-stack
PKG_VERSION:=0.8.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://sourceforge.net/projects/bacnet/files/$(PKG_NAME)/$(PKG_NAME)-$(PKG_VERSION)
PKG_MD5SUM:=cb7d0bc58bfe36ce3789923b9e5acd2d

include $(INCLUDE_DIR)/package.mk

define Package/bacnet-stack
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=BACnet Protocol Stack
  URL:=http://sourceforge.net/projects/bacnet/
  DEPENDS:=+libpthread +librt
endef

define Package/bacnet-stack/description
BACnet - Data Communication Protocol for Building Automation and Control Networks - see www.bacnet.org . This BACnet library provides an application layer, network layer and MAC layer communications services for Win32, Linux, RTOS, or microcontroller.
endef

TARGET_CFLAGS += $(FPIC)

	MAKE_FLAGS += \
		CFLAGS="-I $(PKG_BUILD_DIR)/include -I $(PKG_BUILD_DIR)/ports/linux -I $(PKG_BUILD_DIR)/demo/object $(TARGET_CFLAGS)" \
	LDFLAGS="-L $(PKG_BUILD_DIR)/lib $(TARGET_LDFLAGS)"  

define Package/bacnet-stack/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacarf $(1)/usr/bin/bacarf
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacdcc $(1)/usr/bin/bacdcc
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/baciamr $(1)/usr/bin/baciamr
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacrbdt $(1)/usr/bin/bacrbdt
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacrp $(1)/usr/bin/bacrp
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacrpd.sh $(1)/usr/bin/bacrpd.sh
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacscov $(1)/usr/bin/bacscov
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacts $(1)/usr/bin/bacts
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacwi $(1)/usr/bin/bacwi
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacwp $(1)/usr/bin/bacwp
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bvlc.sh $(1)/usr/bin/bvlc.sh
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/mstpcrc $(1)/usr/bin/mstpcrc
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacawf $(1)/usr/bin/bacawf
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacepics $(1)/usr/bin/bacepics
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacinitr $(1)/usr/bin/bacinitr
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacrd $(1)/usr/bin/bacrd
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacrpm $(1)/usr/bin/bacrpm
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacserv $(1)/usr/bin/bacserv
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacucov $(1)/usr/bin/bacucov
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacwh $(1)/usr/bin/bacwh
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/bacwir $(1)/usr/bin/bacwir
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/mstpcap $(1)/usr/bin/mstpcap
endef

$(eval $(call BuildPackage,bacnet-stack))
