## Kernel module for mt7921 on Asahi Linux

This is a fork of https://github.com/openwrt/mt76 that specifically builds the MT7921 driver for Asahi Linux (Arch running on Macbook hardware).

This enable you to use more external wifi dongles with MediaTek chipset. The original omarchy-mac kernel deliberately stripped those modules to reduce size.

## Work done
- Update headers to match newer Linux kernel versions
- Add missing support functions without including the whole library

## License
No warranty, since the original code is libre please use it as you see fit following the original license.
