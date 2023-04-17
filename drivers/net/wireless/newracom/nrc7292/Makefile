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
		nrc-s1g.o \

ccflags-y := \
	-DDEBUG \
	-DCONFIG_NRC_HIF_CSPI \
	-DENABLE_DYNAMIC_PS \
	-DCONFIG_MAC80211_MESH

ccflags-$(CONFIG_SOC_MT7620) += -DCONFIG_SPI_HALF_DUPLEX -DCONFIG_SUPPORT_JMP

ldflags-y += -T$(BACKPORT_DIR)/drivers/net/wireless/newracom/nrc7292/nrc.lds
