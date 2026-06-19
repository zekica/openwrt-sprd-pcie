include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=sprd-pcie
PKG_VERSION:=1.1.8
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define KernelPackage/sprd-pcie
  SUBMENU:=Other modules
  TITLE:=Quectel PCIe driver
  FILES:=$(PKG_BUILD_DIR)/sprd_pcie.ko
  AUTOLOAD:=$(call AutoLoad,10,sprd_pcie)
endef

define KernelPackage/sprd-pcie/description
  Quectel PCIe driver for 5G modems
endef

# Step to copy your local source code into the build target directory
define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/ -r
endef

# Step to compile using the OpenWrt kernel flags
define Build/Compile
	+$(KERNEL_MAKE) $(PKG_JOBS) \
		$(PKG_MAKE_FLAGS) \
		M="$(PKG_BUILD_DIR)" \
		modules
endef

$(eval $(call KernelPackage,sprd-pcie))
