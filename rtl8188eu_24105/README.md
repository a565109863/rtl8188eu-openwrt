<<<<<<< HEAD
# rtl8188eu-for-openwrt
rtl8188eu for openwrt
=======
# RTL8188eu kernel driver for OpenWRT
## Patches
### Generated with
```
git clone https://github.com/InfiRandia/rtl8188eu # a fork with openwrt and new kernel patches
git checkout openwrt
git format-patch main
```

## Add to OpenWRT repository
### 1. Clone to openwrt repository
```
cd "[PATHTO_OPENWRT_REPO]/package/kernel"
git clone https://github.com/InfiRandia/rtl8188eu-openwrt.git rtl8188eu
```

### 2. Select driver in `make menuconfig`
Kernel Modules > Wireless Drivers > kmod-rtl8188eu
>>>>>>> 9f5bf5bf41e89e540452c1f7baf5aac8e6f1f40e
