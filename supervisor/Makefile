#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=supervisor
PKG_VERSION:=3.1.3
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/s/supervisor/
PKG_MD5SUM:=aad263c4fbc070de63dd354864d5e552

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/supervisor
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=supervisor
  URL:=http://supervisord.org/
  DEPENDS:=+python +meld3 +elementtree
  MAINTAINER:=Chris McDonough
endef

define Package/supervisor/description
Supervisor is a client/server system that allows its users to
control a number of processes on UNIX-like operating systems.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/supervisor/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,supervisor))
