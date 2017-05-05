#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=linux-packages

PKG_MAINTAINER:=Alexandru Ardelean <ardeleanalex@gmail.com>

PKG_BUILD_DIR:=$(KERNEL_BUILD_DIR)/packages

PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=

include $(INCLUDE_DIR)/package.mk

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/linux-packages
  HIDDEN:=1
  TITLE:=Virtual kernel package (in packages feed)
  VERSION:=$(LINUX_VERSION)-$(LINUX_RELEASE)-$(LINUX_VERMAGIC)
  URL:=http://www.kernel.org/
endef

define Package/linux-packages/description
  Kernel modules built from OpenWrt's kernel, that are not
  present in OpenWrt core, but are required in the packages feed.
endef

define Package/linux-packages/install
	:
endef

include $(sort $(wildcard ./modules/*.mk))

$(eval $(call BuildPackage,linux-packages))
