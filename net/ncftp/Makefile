#
# Copyright (C) 2010-2024 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ncftp
PKG_VERSION:=3.3.0
PKG_RELEASE:=1

PKG_INSTALL:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-src.tar.gz
PKG_SOURCE_URL:=https://www.ncftp.com/public_ftp/ncftp
PKG_MD5SUM:=886d757702133f5d6d105a9af6acd8f4

include $(INCLUDE_DIR)/package.mk

define Package/ncftp/Default
 SECTION:=net
 CATEGORY:=Network
 SUBMENU:=File Transfer
 TITLE:=NcFTP Client
 URL:=http://www.ncftpd.com/
endef

define Package/ncftp/Default/description
 NcFTP Client (also known as just NcFTP) is a set of FREE application
 programs implementing the File Transfer Protocol (FTP).
endef

define Package/ncftp
$(call Package/ncftp/Default)
 TITLE+= (main program)
endef

define Package/ncftp/description
$(call Package/ncftp/Default/description)
 Main program.
endef

define Package/ncftp-utils
$(call Package/ncftp/Default)
 TITLE+= (utilities)
endef

define Package/ncftp-utils/description
$(call Package/ncftp/Default/description)
 Utilities.
endef

define Package/ncftp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/ncftp $(1)/usr/bin/
endef

define Package/ncftp-utils/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/ncftp{batch,get,ls,put,spooler} \
		$(1)/usr/bin/
endef

$(eval $(call BuildPackage,ncftp))
$(eval $(call BuildPackage,ncftp-utils))
