include $(TOPDIR)/rules.mk

PKG_NAME:=lua-binaryheap
PKG_VERSION:=0.4
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/Tieske/binaryheap.lua/tar.gz/version_0v4?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=10b1b6c6f2d22560f512f9896a6672ec5ae0eea1390ff8e662be1d5d9625b438

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/binaryheap.lua-version_0v4

include $(INCLUDE_DIR)/package.mk

define Package/lua-binaryheap
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-binaryheap
  URL:=https://github.com/Tieske/binaryheap.lua
  DEPENDS:=+lua
endef

define Package/lua-binaryheap/description
	Binary heap implementation in Lua
endef

define Build/Compile
	:
endef

define Package/lua-binaryheap/install
	$(INSTALL_DIR) $(1)/usr/share/lua/common
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/binaryheap.lua $(1)/usr/share/lua/common/binaryheap.lua
endef

$(eval $(call BuildPackage,lua-binaryheap))
