#
# Copyright (C) 2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=jsonpickle
PKG_VERSION:=0.9.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/j/jsonpickle
PKG_MD5SUM:=579a44c19ae55af83cb7b0437dfbe7e3

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/jsonpickle
  SECTION:=language-python
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=jsonpickle
  URL:=http://jsonpickle.github.io/
  DEPENDS:=+python +simplejson
  MAINTAINER:=John Paulett
endef

define Package/jsonpickle/description
Python library for serializing any arbitrary object graph into JSON
jsonpickle converts complex Python objects to and from JSON.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/jsonpickle/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,jsonpickle))
