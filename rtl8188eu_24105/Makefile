include $(TOPDIR)/rules.mk

PKG_NAME:=rtl8188eu
PKG_RELEASE=1

PKG_SOURCE_URL:=https://github.com/pritam-singh-db/rtl8188eu.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2025-12-11
PKG_SOURCE_VERSION:=857b0876a45eb55b467336b61014773ceb2ac373
PKG_MIRROR_HASH:=skip

<<<<<<< HEAD
PKG_BUILD_PARALLEL:=1

=======
>>>>>>> 9f5bf5bf41e89e540452c1f7baf5aac8e6f1f40e
STAMP_CONFIGURED_DEPENDS := $(STAGING_DIR)/usr/include/mac80211-backport/backport/autoconf.h

include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

define KernelPackage/rtl8188eu
  SUBMENU:=Wireless Drivers
  TITLE:=Driver for RTL8188EU Wireless Chipsets
<<<<<<< HEAD
  DEPENDS:= +kmod-cfg80211 +rtl8188eu-firmware +kmod-usb-core +kmod-mac80211 +@DRIVER_11N_SUPPORT
=======
  DEPENDS:= +kmod-cfg80211 +rtl8188eu-firmware +kmod-usb-core +@DRIVER_11N_SUPPORT
>>>>>>> 9f5bf5bf41e89e540452c1f7baf5aac8e6f1f40e
  FILES:=$(PKG_BUILD_DIR)/8188eu.ko
  AUTOLOAD:=$(call AutoProbe,8188eu)
  PROVIDES:=kmod-rtl8188eu
endef

<<<<<<< HEAD
define KernelPackage/rtl8188eu/description
	Realtek RTL8188EU USB WiFi driver
endef

BACKPORT_DIR:=$(STAGING_DIR)/usr/include/mac80211-backport

NOSTDINC_FLAGS := \
	$(KERNEL_NOSTDINC_FLAGS) \
	-I$(PKG_BUILD_DIR)/include \
	-I$(BACKPORT_DIR) \
	-I$(BACKPORT_DIR)/uapi \
=======
NOSTDINC_FLAGS := \
	$(KERNEL_NOSTDINC_FLAGS) \
	-I$(PKG_BUILD_DIR) \
	-I$(PKG_BUILD_DIR)/include \
	-I$(STAGING_DIR)/usr/include/mac80211-backport \
	-I$(STAGING_DIR)/usr/include/mac80211-backport/uapi \
>>>>>>> 9f5bf5bf41e89e540452c1f7baf5aac8e6f1f40e
	-I$(STAGING_DIR)/usr/include/mac80211 \
	-I$(STAGING_DIR)/usr/include/mac80211/uapi \
	-include backport/backport.h

CT_MAKEDEFS += CONFIG_RTL8188EU=m

<<<<<<< HEAD
EXTRA_CFLAGS:= \
  -DCONFIG_IOCTL_CFG80211 \
  -DRTW_USE_CFG80211_STA_EVENT \
  -D_LINUX_BYTEORDER_SWAB_H \
  -DCONFIG_RADIO_WORK \
  -DCONFIG_POWER_SAVING=0 \
  -DBUILD_OPENWRT

ifeq ($(CONFIG_BIG_ENDIAN),y)
	EXTRA_CFLAGS += -DCONFIG_BIG_ENDIAN
else
	EXTRA_CFLAGS += -DCONFIG_LITTLE_ENDIAN
endif

define Build/Compile
	+$(KERNEL_MAKE) $(PKG_JOBS) \
		M="$(PKG_BUILD_DIR)" \
		NOSTDINC_FLAGS="$(NOSTDINC_FLAGS)" \
		USER_EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
		$(CT_MAKEDEFS) modules

=======
NOSTDINC_FLAGS+=-DCONFIG_IOCTL_CFG80211 -DRTW_USE_CFG80211_STA_EVENT -DBUILD_OPENWRT -D_LINUX_BYTEORDER_SWAB_H -DCONFIG_LITTLE_ENDIAN

define Build/Compile
	+$(MAKE) $(PKG_JOBS) -C "$(LINUX_DIR)" \
	$(KERNEL_MAKE_FLAGS) \
	M="$(PKG_BUILD_DIR)" \
	NOSTDINC_FLAGS="$(NOSTDINC_FLAGS)" \
	$(CT_MAKEDEFS) modules
>>>>>>> 9f5bf5bf41e89e540452c1f7baf5aac8e6f1f40e
endef

$(eval $(call KernelPackage,rtl8188eu))
