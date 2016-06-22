include $(TOPDIR)/rules.mk

PKG_NAME:=python-regex
PKG_VERSION:=2016.06.22
PKG_RELEASE:=1

PKG_SOURCE:=python-regex-2016.06.22.tar.gz
PKG_SOURCE_URL:=https://download.alephobjects.com/ao/openwrt/src/

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-regex
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-regex
  URL:=https://bitbucket.org/mrabarnett/mrab-regex/src
  DEPENDS:=+python
endef

define Package/python-regex/description
  This new regex implementation is intended eventually to replace Python's current re module implementation.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" )
endef

define Package/python-regex/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call PyPackage,python-regex))
$(eval $(call BuildPackage,python-regex))
