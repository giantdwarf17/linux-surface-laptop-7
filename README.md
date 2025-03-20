# Linux on the Surface Laptop 7 (ARM)

These are my notes for getting Linux working on the Surface Laptop 7 (ARM).

Based on the [Ubuntu Concept image](https://discourse.ubuntu.com/t/ubuntu-24-10-concept-snapdragon-x-elite/48800/1)

**Disclaimer:** I have no experience with upstreaming patches, the patch review process, Linux coding conventions, etc. **at all**, so for now I'm just documenting everything here in the hope that more knowledgable people can help!

## What's working

| **Feature**               | **Working?** | **Notes**                                                                                                                                                  |
|---------------------------|:------------:|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NVMe                      |       ✅      |                                                                                                                                                            |
| Graphics                  |       ✅      | Requires qcom-firmware-extract                                                                                          |
| Backlight                 |       ❓      | Untested                                                                                                                                                   |
| USB                       |   Partially  | USB-A and USB-C ports are working. Have not tested USB over Surface Connector              |
| USB-C display output      |       ❓      |                                                                                                                                                            |
| Wi-Fi                     |       ❌      |         |
| Bluetooth                 |       ❌      |                                                                                                                                                            |
| Audio                     |       ❌      |                                                                                                                      |
| Touchscreen               |       ❌      |                                                                                                                                                            |
| Touchpad               |       ❌      |                                                                                                                                                            |
| Pen                       |       ❌      |                                                                                                                                                            |
| Keyboard             |       ✅      |                                                                                        |
| Lid switch/suspend        |       ✅      | Seems to be working.                                                                                                                                       |
| Cameras (and status LEDs) |       ❌      |                                                                                                                                                            |

> [!WARNING]
> Without installing the firmware, many hardware components will be broken!

### Firmware blobs

Firmware blobs that cannot be distributed here are needed from the stock Windows installation to get certain devices working.

A script to copy the blobs from an existing windows install is present in the [Ubuntu Concept image](https://launchpad.net/~ubuntu-concept/+archive/ubuntu/x1e).
