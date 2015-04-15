#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=nose
PKG_VERSION:=1.3.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/n/nose
PKG_MD5SUM:=6ed7169887580ddc9a8e16048d38274d

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/nose
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=nose
  URL:=http://readthedocs.org/docs/nose/
  DEPENDS:=+python 
  MAINTAINER:=Jason Pellerin
endef

define Package/nose/description
nose extends the test loading and running features of unittest, making it easier to write, find and run tests.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/nose/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,nose))
