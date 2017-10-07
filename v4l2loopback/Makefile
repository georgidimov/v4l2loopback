#
# Copyright (C) 2008-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=v4l2loopback
PKG_VERSION:=0.10.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/umlaeute/v4l2loopback
PKG_SOURCE_VERSION:=79a71bf7308be5faf8d97c72107688f8c6da1733


PKG_MAINTAINER:=Georgi Dimov <georgidimov94@gmail.com>

include $(INCLUDE_DIR)/package.mk

define KernelPackage/v4l2loopback
  SUBMENU:=Video Support
  TITLE:=v4l2loopback kernel module
  FILES:=$(PKG_BUILD_DIR)/v4l2loopback.ko
  DEPENDS:=+kmod-video-core
  AUTOLOAD:=$(call AutoLoad,30,v4l2loopback,1)
endef

define KernelPackage/v4l2loopback/description
	This module allows you to create "virtual video devices".
	Normal (v4l2) applications will read these devices as if
	they were ordinary video devices, but the video will not be
	read from e.g. a capture card but instead it is generated
	by another application. 
endef

MAKE_OPTS:= \
	ARCH="$(LINUX_KARCH)" \
	CROSS_COMPILE="$(TARGET_CROSS)" \
	SUBDIRS="$(PKG_BUILD_DIR)"

define Build/Compile
	$(MAKE) -C "$(LINUX_DIR)" \
		$(MAKE_OPTS) \
		modules
endef

$(eval $(call KernelPackage,v4l2loopback))
