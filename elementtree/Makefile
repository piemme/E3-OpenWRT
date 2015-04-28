#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=elementtree
PKG_VERSION:=1.0.2-20050316
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://effbot.org/media/downloads/
PKG_MD5SUM:=e1b21716be8bfff8bf192fc3880ad008

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/elementtree
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=elementtree
  URL:=http://effbot.org/zone/element-index.htm
  DEPENDS:=+python 
  MAINTAINER:=Fredrik Lundh
endef

define Package/elementtree/description
The Element type is a flexible container object, designed to store hierarchical data structures in memory. Element structures can be converted to and from XML.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/elementtree/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,elementtree))
