#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=setuptools
PKG_VERSION:=15.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/s/setuptools/
PKG_MD5SUM:=a9028a9794fc7ae02320d32e2d7e12ee

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/setuptools
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=setuptools
  URL:=https://bitbucket.org/pypa/setuptools
  DEPENDS:=+python 
  MAINTAINER:=Python Packaging Authority
endef

define Package/setuptools/description
Easily download, build, install, upgrade, and uninstall Python packages
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/setuptools/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,setuptools))
