#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=pymodbus
PKG_VERSION:=1.2.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pymodbus/
PKG_MD5SUM:=90f9b63cf962b3032dc60ad81a185f34

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-modbus
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python-modbus
  URL:=http://code.google.com/p/pymodbus/
  DEPENDS:=+python +python-twisted +python-serial
  MAINTAINER:=Galen Collins
endef

define Package/python-modbus/description
Pymodbus aims to be a fully implemented modbus protocol stack implemented using twisted. Its orignal goal was to allow simulation of thousands of modbus devices on a single machine for monitoring software testing.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-modbus/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-modbus))
