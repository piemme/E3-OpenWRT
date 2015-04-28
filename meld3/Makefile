#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=meld3
PKG_VERSION:=1.0.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/m/meld3/
PKG_MD5SUM:=3ccc78cd79cffd63a751ad7684c02c91

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/meld3
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=meld3
  URL:=http://supervisord.org/
  DEPENDS:=+python +setuptools +elementtree
  MAINTAINER:=Chris McDonough
endef

define Package/meld3/description
meld3 is an HTML/XML templating system for Python which keeps template markup and dynamic rendering logic separate from one another
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/meld3/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,meld3))
