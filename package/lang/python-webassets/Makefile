include $(TOPDIR)/rules.mk

PKG_NAME:=python-webassets
PKG_VERSION:=0.11.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://download.alephobjects.com/ao/openwrt/src/

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-webassets
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-webassets
  URL:=https://github.com/miracle2k/webassets/
  DEPENDS:=+python
endef

define Package/python-webassets/description
  Asset management application for Python web development - use it to merge and compress your JavaScript and CSS files.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" )
endef

define Package/python-webassets/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call PyPackage,python-webassets))
$(eval $(call BuildPackage,python-webassets))
