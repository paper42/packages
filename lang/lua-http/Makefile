include $(TOPDIR)/rules.mk

PKG_NAME:=lua-http
PKG_VERSION:=0.4
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/daurnimator/lua-http/tar.gz/v$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=d2e3cb9bc04cab70ac4f19351bc74b0dcd8b16cfc2563aa77256eb3a43b3b9e0

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE.md

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DEPENDS:=luarocks/host
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-http
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-http
  URL:=https://github.com/daurnimator/lua-http
  DEPENDS:=+lua +lua-bit32 +lpeg +lua-compat53 +lua-lpeg_patterns +lua-ossl +lua-binaryheap +lua-basexx +lua-fifo
endef

define Package/lua-http/description
	HTTP Library for Lua. Supports HTTP(S) 1.0, 1.1 and 2.0; client and server.
endef

define Build/Compile
  cd $(PKG_BUILD_DIR) && \
  luarocks make --tree=build http-$(PKG_VERSION)-0.rockspec \
    LUA_LIBDIR=$(STAGING_DIR)/usr/lib/lua \
    LUA_PKGNAME=lua5.1 \
    CC="$(TARGET_CC)" LD="$(TARGET_CC)" \
    CFLAGS="$(TARGET_CFLAGS) $(FPIC)" \
    LDFLAGS="$(TARGET_LDFLAGS)"
  #$(RM) -rf $(PKG_BUILD_DIR)/build/lib/luarocks
endef

define Package/lua-http/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/http.so $(1)/usr/lib/lua
endef

#define Package/lua-ev/install
#	$(INSTALL_DIR) $(1)/usr/lib/lua
#	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ev.so $(1)/usr/lib/lua
#endef

$(eval $(call BuildPackage,lua-http))
