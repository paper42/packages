include $(TOPDIR)/rules.mk

PKG_NAME:=lua-compat53
PKG_VERSION:=0.10
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/lunarmodules/lua-compat-5.3/tar.gz/v$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=d1ed32f091856f6fffab06232da79c48b437afd4cd89e5c1fc85d7905b011430

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/lua-compat-5.3-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=luarocks/host
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-compat53
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-compat53
  URL:=https://github.com/daurnimator/lua-compat53
  DEPENDS:=+lua
endef

define Package/lua-compat53/description
	Compatibility module providing Lua-5.3-style APIs for Lua 5.2 and 5.1
endef

define Build/Compile
  cd $(PKG_BUILD_DIR) && \
  luarocks make --tree=build rockspecs/compat53-scm-0.rockspec \
    LUA_LIBDIR=$(STAGING_DIR)/usr/lib/lua \
    LUA_PKGNAME=lua5.1 \
    CC="$(TARGET_CC)" LD="$(TARGET_CC)" \
    CFLAGS="$(TARGET_CFLAGS) $(FPIC)" \
    LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/lua-compat53/install
	$(CP) $(PKG_BUILD_DIR)/build/* $(1)/
endef

$(eval $(call BuildPackage,lua-compat53))
