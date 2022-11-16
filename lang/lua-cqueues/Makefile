include $(TOPDIR)/rules.mk

PKG_NAME:=lua-cqueues
PKG_VERSION:=20200726
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_URL=https://codeload.github.com/wahern/cqueues/tar.gz/rel-$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=9e112edd246da5cfca264314b70325a0b63665cb87a00e45ee3ae4f194000d52

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_BUILD_DIR=$(BUILD_DIR)/cqueues-rel-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/lua-cqueues
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-cqueues
  URL:=https://github.com/wahern/cqueues
  DEPENDS:=+lua +libopenssl
endef

define Package/lua-cqueues/description
	Continuation Queues: Embeddable asynchronous networking, threading, and
	notification framework for Lua on Unix.
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/ \
		LUA_APIS="5.1" \
		ALL_LDFLAGS="$(TARGET_LDFLAGS)" \
		CC="$(TARGET_CC) $(TARGET_CFLAGS) $(TARGET_CPPFLAGS) -fPIC -std=gnu99" \
		LD="$(TARGET_CROSS)ld -shared" \
		all5.1
endef


define Package/lua-cqueues/install
	cd $(PKG_BUILD_DIR); make DESTDIR="$(1)" prefix=/usr install5.1
endef

$(eval $(call BuildPackage,lua-cqueues))
