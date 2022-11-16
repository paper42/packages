include $(TOPDIR)/rules.mk

PKG_NAME:=lua-ossl
PKG_VERSION:=20220711
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/wahern/luaossl/tar.gz/rel-$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=f16c4cd2c880f270c1c73daa0a4bfdd11ae3155b92a2086863731e06d241300b

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE.md

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/luaossl-rel-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lua-ossl
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-ossl
  URL:=https://github.com/wahern/luaossl
  DEPENDS:=+lua +libopenssl
endef

define Package/lua-ossl/description
	HTTP Library for Lua. Supports HTTP(S) 1.0, 1.1 and 2.0; client and server.
endef

define Build/Compile
  cd $(PKG_BUILD_DIR) && make openssl5.1
endef

define Package/lua-ossl/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/5.1
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/5.1/openssl.so $(1)/usr/lib/lua/5.1/
endef

$(eval $(call BuildPackage,lua-ossl))
