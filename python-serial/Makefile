#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=pyserial
PKG_VERSION:=2.7
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pyserial/
PKG_MD5SUM:=794506184df83ef2290de0d18803dd11

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-serial
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python-serial
  URL:=http://code.google.com/p/pyserial/
  DEPENDS:=+python 
  MAINTAINER:=Chris Liechti
endef

define Package/python-serial/description
Python Serial Port Extension for Win32, Linux, BSD, Jython, IronPython
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-serial/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-serial))
