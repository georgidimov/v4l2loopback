# v4l2loopback openwrt/lede feed

### This feed contains Makefiles for:

1. [v4l2loopback](https://github.com/umlaeute/v4l2loopback)
___

## Usage:

### Add v4l2loopback feed in your feeds.conf local file:
```
echo "src-git v4l2loopback https://github.com/georgidimov/v4l2loopback.git" >> feeds.conf
```

### Update your build environment and install the packages:
```
./scripts/feeds update -a
./scripts/feeds install -a
```

### Configure your build:
```
make defconfig
make menuconfig
```

### Select also:
```
    Kernel modules  --->
                        Video Support  --->
                                          <*> kmod-v4l2loopback
```

### And compile:
```
    make -j4
```
