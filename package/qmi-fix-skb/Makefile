include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=qmi-fix-skb
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_BUILD_DIR := $(TOPDIR)/package/qmi-fix-skb

include $(INCLUDE_DIR)/package.mk

define KernelPackage/qmi-fix-skb
  SUBMENU:=Other modules
  TITLE:=Kprobe hotfix for qmi_wwan_f skb headroom
  DEPENDS:=@KPROBES
  FILES:=$(PKG_BUILD_DIR)/qmi_fix_skb.ko
  AUTOLOAD:=$(call AutoProbe,qmi_fix_skb)
endef

define Build/Compile
	$(KERNEL_MAKE) M="$(PKG_BUILD_DIR)" modules
endef

$(eval $(call KernelPackage,qmi-fix-skb))


