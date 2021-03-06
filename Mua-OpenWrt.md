# Mua OpenWrt

## Project List

- https://github.com/robbie-cao/mua-openwrt
- https://github.com/robbie-cao/mua-openwrt-feed
- https://github.com/robbie-cao/mua-mtk-lks7688-feed
- https://github.com/robbie-cao/mua-uboot-7688

## Setup

### openwrt

```
$ git clone git@github.com:robbie-cao/mua-openwrt.git openwrt
```

If you have a git clone of openwrt from https://github.com/openwrt/openwrt.git already, use the following command to swtich git remote track.

**This will quickly switch git remote repository and save time of cloning a fresh copy.**

```
$ cd openwrt (-> assume your openwrt path)
$ git remote -v (-> to check your remote git repository)
$ git remote set-url origin git@github.com:robbie-cao/mua-openwrt.git (-> switch remote repository)
$ git fetch origin --prune (-> sync to new remote repository)
$ git checkout -b board/synnex --track remotes/origin/board/synnex (-> checkout the developing branch for current board)
```

### uboot

```
$ git clone git@github.com:robbie-cao/mua-uboot-7688.git uboot
```

## Build

```
$ cd openwrt
$ ./scripts/feeds update -a
$ ./scripts/feeds install -a

$ cp -f config.default .config
-or-
$ make menuconfig

$ make V=s
```

