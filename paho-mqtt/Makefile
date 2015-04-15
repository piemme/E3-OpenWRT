#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=paho-mqtt
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/paho-mqtt
PKG_MD5SUM:=a6407b74eb5e5411e157be1de5c11366

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/paho-mqtt
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=paho-mqtt
  URL:=http://eclipse.org/paho
  DEPENDS:=+python 
  MAINTAINER:=Roger Light
endef

define Package/paho-mqtt/description
MQTT version 3.1/3.1.1 client class
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/paho-mqtt/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,paho-mqtt))
