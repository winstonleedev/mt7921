## Kernel module for mt7921 on Asahi Linux

This is a fork of https://github.com/openwrt/mt76 that specifically builds the MT7921 driver for Asahi Linux (Arch running on Macbook hardware).

This enable you to use more external wifi dongles with MediaTek chipset. The original omarchy-mac kernel deliberately stripped those modules to reduce size.

## Work done
- Update headers to match newer Linux kernel versions
- Add missing support functions without including the whole library

## How to use
```bash
# Build
make -C /lib/modules/$(uname -r)/build M=$(pwd) CONFIG_MT7921_COMMON=m CONFIG_MT7921U=m modules

# Install
sudo make -C /lib/modules/$(uname -r)/build M=$(pwd) CONFIG_MT7921_COMMON=m CONFIG_MT7921U=m modules_install

# Verify
ls /lib/modules/$(uname -r)/updates/mt7921/
# If this returns something, you're good!

# Enable
sudo depmod -a
sudo modprobe mt7921u

# Plug in the dongle, verify it's active
ip link

# Try it
sudo ip link set wlan<YOUR DONGLE FROM THE ABOVE COMMAND> up

# Enable auto-loading on boot
echo "mt7921u" | sudo tee /etc/modules-load.d/mt7921u.conf
```

## License
No warranty, since the original code is libre please use it as you see fit following the original license.
