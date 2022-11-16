include $(TOPDIR)/rules.mk

PKG_NAME:=lua-lpeg_patterns
PKG_VERSION:=0.5
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/daurnimator/lpeg_patterns/tar.gz/v$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=d1fabf897024822eb2544fd811fc80b85655972804511b9fd8cfea377fb16e0e

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE.md

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR:=$(BUILD_DIR)/lpeg_patterns-$(PKG_VERSION)
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-lpeg_patterns
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-lpeg_patterns
  URL:=https://github.com/daurnimator/lpeg_patterns
  DEPENDS:=+lua +lpeg
endef

define Package/lua-lpeg_patterns/description
	A collection of LPEG patterns
endef

define Build/Compile
	:
endef

define Package/lua-lpeg_patterns/install
	$(INSTALL_DIR) $(1)/usr/share/lua/5.1/lpeg_patterns
	$(CP) $(PKG_BUILD_DIR)/lpeg_patterns/* $(1)/usr/share/lua/5.1/lpeg_patterns/
endef

$(eval $(call BuildPackage,lua-lpeg_patterns))
