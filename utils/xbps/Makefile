include $(TOPDIR)/rules.mk

PKG_NAME:=xbps
PKG_VERSION:=0.59.1
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/void-linux/xbps/tar.gz/$(PKG_VERSION)?
PKG_HASH:=0cbd8d5f23a62047c75974bca21da9f004a94efffd7f37c68562a8dbc869fb2a

PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>
PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

CONFIGURE_VARS += TOPDIR=$(PKG_BUILD_DIR)

define Package/xbps
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=xbps package manager
  DEPENDS:=+zlib +libarchive
  URL:=$(PKG_SOURCE_URL)
endef

define Package/xbps/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/var/db/xbps/keys
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/var/db/xbps/keys/* $(1)/var/db/xbps/keys/

	$(INSTALL_DIR) $(1)/usr/share/xbps.d
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/share/xbps.d/* $(1)/usr/share/xbps.d/
endef

$(eval $(call BuildPackage,xbps))
