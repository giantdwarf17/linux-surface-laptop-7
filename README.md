# Linux on the Surface Laptop 7 (ARM)

These are my notes for getting Linux working on the Surface Laptop 7 (ARM).

Based on the [Ubuntu Concept image](https://discourse.ubuntu.com/t/ubuntu-24-10-concept-snapdragon-x-elite/48800/1)

**Disclaimer:** I have no experience with upstreaming patches, the patch review process, Linux coding conventions, etc. **at all**, so for now I'm just documenting everything here in the hope that more knowledgable people can help!

## What's working

| **Feature**               | **Working?** | **Notes**                                                                                                                                                  |
|---------------------------|:------------:|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NVMe                      |       ✅      |                                                                                                                                                            |
| Graphics                  |       ✅      | Requires firmware                                                                                          |
| Backlight                 |       ✅      |                                                                                                                                                    |
| USB                       |   Partially  | USB-A and USB-C ports are working. Have not tested USB over Surface Connector              |
| USB-C display output      |       ❓      |                                                                                                                                                            |
| Wi-Fi                     |       ✅      | Requires kernel patch [patches/0001-wifi-rfkill-hack.patch](patches/0001-wifi-rfkill-hack.patch)        |
| Bluetooth                 |       ❌      |                                                                                                                                                            |
| Audio                     |       ❌      |                                                                                                                      |
| Touchscreen               |       ❌      |                                                                                                                                                            |
| Touchpad               |       ❌      |                                                                                                                                                            |
| Keyboard             |       ✅      |                                                                                        |
| Lid switch/suspend        |       ✅      | Seems to be working.                                                                                                                                       |
| Webcam |       ❌      |                                                                                                                                                            |

> [!WARNING]
> Without installing the firmware, many hardware components will be broken!

### Firmware blobs

Firmware blobs that cannot be distributed here are needed from the stock Windows installation to get certain devices working. See https://github.com/linux-surface/linux-surface/issues/1590#issuecomment-2738689008.

## Tips & Tricks

### Booting the image
Attempting to boot the ubuntu-concept image will fail unless you specify the device tree in the GRUB config. 

"The best way to manually boot the correct dtb would be pressing 'e' in grub when it shows the boot options and then replacing '$dtb' with 'devicetree /casper/x1e80100-microsoft-romulus13.dtb'"
- Tobias Heider https://bugs.launchpad.net/ubuntu-concept/+bug/2084951/comments/6

### Fixing Firefox crashes
There is an issue in the Firefox snap package that causes it to crash whenever you use the scroll wheel. The workaround is to switch to the .deb version.

I did so by following these instructions: https://askubuntu.com/a/1404401

### Installing KDE
This is by no means neccessary, but personally I strongly prefer KDE and have been manually switching until support is expanded to more images. This post describes how to do so correctly: https://askubuntu.com/a/1406054
