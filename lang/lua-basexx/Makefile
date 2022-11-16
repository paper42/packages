include $(TOPDIR)/rules.mk

PKG_NAME:=lua-basexx
PKG_VERSION:=0.4.1
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/aiq/basexx/tar.gz/v$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=ff62b00446df1181a9cd20ba970c3c8493165d262142e10d069ee3de6337dfe6

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/basexx-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lua-basexx
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-basexx
  URL:=https://github.com/aiq/basexx
  DEPENDS:=+lua
endef

define Package/lua-basexx/description
 A Lua library which provides base2(bitfield), base16(hex),
 base32(crockford/rfc), base64(rfc/url), base85(z85) decoding and encoding.
endef

define Build/Compile
	:
endef

define Package/lua-basexx/install
	$(INSTALL_DIR) $(1)/usr/share/lua/5.1
	$(CP) $(PKG_BUILD_DIR)/lib/* $(1)/usr/share/lua/5.1/
endef

$(eval $(call BuildPackage,lua-basexx))
