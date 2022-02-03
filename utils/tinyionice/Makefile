#
# Copyright (C) 2022 CZ.NIC, z. s. p. o. (https://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tinyionice
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/xyproto/tinyionice/tar.gz/${PKG_VERSION}?
PKG_HASH:=503f91ab0af4846f34f0444ab71c4b286123f0044a4964f1ae781486c617f2e2

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Michal Vasilek <michal.vasilek@nic.cz>

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tinyionice
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Independent fork of ionice from util-linux
  URL:=https://github.com/xyproto/tinyionice
endef

define Package/tinyionice/Default/description
  Independent fork of ionice from util-linux
endef

define Package/tinyionice/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tinyionice))
