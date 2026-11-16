# TWRP device tree — Samsung Galaxy J2 Prime SM-G532G/DS

Initial device-tree scaffold for the Samsung Galaxy J2 Prime (`grandppltedx`, MediaTek MT6737T).

> **Not a flashable recovery yet.** The proprietary/prebuilt kernel (`kernel`) and MediaTek device tree image (`dt.img`) are not included. Do not build or flash an image until these files, the boot-image header settings, and the partition map have been verified against your exact SM-G532G/DS firmware. A wrong recovery image can prevent the phone from booting.

## Build

This tree follows the legacy Omni/TWRP device-tree layout. Place it at `device/samsung/grandppltedx` in a compatible TWRP/Omni source checkout. Add a compatible kernel as `device/samsung/grandppltedx/kernel` and the matching `dt.img` before building. Then, from the source root, use the build instructions for that source branch, typically:

```sh
. build/envsetup.sh
lunch omni_grandppltedx-eng
mka recoveryimage
```

The target and commands depend on the TWRP/Omni branch; this initial scaffold has not been built or tested.

## Before testing

1. Confirm the full model is `SM-G532G/DS` and record the firmware build.
2. Compare `recovery.fstab` block paths and partition names with the stock recovery/firmware for this exact variant.
3. Confirm kernel, DT image, boot-image header offsets, recovery partition size, and Android/TWRP branch compatibility.
4. Keep a stock recovery/firmware backup and use a known recovery method to restore it.
5. Do not flash images for `SM-G532F`, `SM-G532M`, or another variant unless compatibility is independently verified.
