#
# Copyright (c) 2015 Quatanium Co., Ltd.
#
# Licensed under MIT.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
PKG_NAME:=cffi
PKG_VERSION:=1.9.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/a1/32/e3d6c3a8b5461b903651dd6ce958ed03c093d2e00128e3f33ea69f1d7965
PKG_MD5SUM:=b8fa7ccb87790531db3316ab17aa8244
PKG_BUILD_DEPENDS:=python python-setuptools pycparser

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-cffi
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python-cffi
	URL:=http://cffi.readthedocs.org/
	DEPENDS:=+libffi +python +pycparser
endef

define Package/python-cffi/description
	Foreign Function Interface for Python calling C code.
endef

define Build/Compile
	$(call Build/Compile/PyMod,, \
		install --prefix=/usr --root=$(PKG_INSTALL_DIR), \
	)
endef

define Package/python-cffi/install
$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-cffi))

