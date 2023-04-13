#
# Newracom 802.11ah Wi-Fi halow driver
#
#######################################################

#ccflags-y += -Wall -Werror -g
ccflags-y += -Wall -Werror


M_SRC = nrc7292

obj-$(CPTCFG_NRC7292) += $(M_SRC).o

$(M_SRC)-objs = \
		nrc-mac80211.o \
		nrc-trx.o \
		nrc-init.o \
		nrc-debug.o \
		hif.o \
		wim.o \
		nrc-fw.o \
		nrc-netlink.o \
		nrc-hif-cspi.o \
		mac80211-ext.o \
		nrc-stats.o \
		nrc-pm.o \
		nrc-dump.o \
		nrc-bd.o \
		nrc-recovery.o

ccflags-y := \
	-DDEBUG \
	-DBUILD_UMAC_DRIVER \
	-DCONFIG_NRC_HIF_CSPI \
	-DCONFIG_MAC80211_MESH
	#-DENABLE_HW_RESET
	#-DCONFIG_NRC_HIF_SDIO
	#-DCONFIG_NRC_HIF_DEBUG \
	#-DCONFIG_NRC_HIF_UART \
	#-DCONFIG_NRC_HIF_AH_UART \
	#-DCONFIG_NRC_HIF_SSP

ccflags-$(CONFIG_SOC_MT7620) += -DCONFIG_SUPPORT_MT76x8 -DCONFIG_SUPPORT_JMP

ldflags-y += -T$(BACKPORT_DIR)/drivers/net/wireless/newracom/nrc7292/nrc.lds
