# OpenWrt feed for Quectel's SPRD PCIe Driver

Based on version 1.1.9, patched to compile on Linux 6.6 to 6.18, compatible with OpenWrt 24.10, 25.12 and main branches.

## Usage

Using your own copy of the buildroot or the OpenWrt SDK, add a new line in `feeds.conf.default`:

```
src-git sprdpcie https://github.com/zekica/openwrt-sprd-pcie
```

Update packages from feeds:

```
./scripts/feeds update -a
./scripts/feeds install -a
```

Enable it in menuconfig and build the system or build only the module itself:

```
make -j`nproc` package/sprd-pcie/compile
```

