include $(TOPDIR)/rules.mk

PKG_NAME:=lua-fifo
PKG_VERSION:=0.2
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/daurnimator/fifo.lua/tar.gz/$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=85cad0c2f9eac1cd3e08c5134feb655e0b928e1e22363c3ef3293a194c0eb53f

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/fifo.lua-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lua-fifo
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-fifo
  URL:=https://github.com/daurnimator/fifo.lua
  DEPENDS:=+lua
endef

define Package/lua-fifo/description
	A lua library/'class' that implements a FIFO. Objects in the fifo can
	be of any type, including nil.
endef

define Build/Compile
	:
endef

define Package/lua-fifo/install
	$(INSTALL_DIR) $(1)/usr/share/lua/5.1
	$(CP) $(PKG_BUILD_DIR)/fifo.lua $(1)/usr/share/lua/5.1/fifo.lua
endef

$(eval $(call BuildPackage,lua-fifo))
