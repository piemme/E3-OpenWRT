#
# Copyright (C) 2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=parted
PKG_VERSION:=3.2
PKG_RELEASE:=1

PKG_SOURCE:=parted-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNU/parted
PKG_MD5SUM:=0247b6a7b314f8edeb618159fa95f9cb

include $(INCLUDE_DIR)/package.mk

define Package/parted
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=disc
	DEFAULT:=y
	TITLE:=GNU Parted manipulates partition tables
	URL:=http://www.gnu.org/software/parted/
	DEPENDS:= +libuuid +libreadline +libncurses +libdevmapper +libblkid +libiconv
endef

define Package/parted/description
	GNU Parted manipulates partition tables. This is useful for creating
	space for new operating systems, reorganizing disk usage, copying data
	on hard disks and disk imaging. The package contains a library,
	libparted, as well as well as a command-line frontend, parted,
	which can also be used in scripts.
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/lib/libiconv-stub/include
TARGET_LDFLAGS += -L$(STAGING_DIR)/usr/lib/libiconv-stub/lib -liconv

define Package/parted/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/libparted/.libs/*.so* $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/parted/.libs/parted $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,parted))
