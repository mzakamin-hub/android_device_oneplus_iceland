# android_device_oneplus_iceland

The Android device tree for the OnePlus Pad 4 (`iceland`, model OPD2514), for LineageOS 24.0 (branch `lineage-24.0`,
the default branch). It holds the files that describe the device to the Android build: the product and board makefiles,
the init and SELinux files, the system properties, the framework overlays, the audio and input configuration, and the
list of proprietary files the device needs.

## Where it fits

- The install guide in [iceland-mainline](https://github.com/mzakamin-hub/iceland-mainline#manual-install) names
  LineageOS 24.0 as the Android system the install was tested from. This repository is the device tree for that
  LineageOS version. The Linux guides do not use it.
- The proprietary files are in [proprietary_vendor_oneplus_iceland](https://github.com/mzakamin-hub/proprietary_vendor_oneplus_iceland).
  `iceland-vendor.mk` expects that tree at `vendor/oneplus/iceland`.
- `lineage.dependencies` also names `android_device_oneplus_sm8850-common` (`device/oneplus/sm8850-common`). That tree is
  not in this repository.

## What is in it

| Path | Content |
|---|---|
| `AndroidProducts.mk`, `lineage_iceland.mk`, `device.mk` | the product definitions (product `lineage_iceland`, device `iceland`) |
| `BoardConfig.mk`, `board-info.txt` | the board configuration |
| `init/` | `init.iceland.rc` |
| `sepolicy/` | SELinux policy additions |
| `properties/` | system properties, including build properties per region code, and the vendor and ODM properties |
| `overlay/` | resource overlays for the framework, the system UI, settings, Wi-Fi and the pen |
| `configs/` | audio, display, input (`idc`, `kl`) and SSG configuration |
| `proprietary-files.txt`, `proprietary-firmware.txt` | the proprietary files and firmware this tree expects from the vendor tree |
| `extract-files.py`, `setup-makefiles.py` | the LineageOS scripts that copy the proprietary files and regenerate the makefiles |

## State

- The branch `lineage-24.0` has 344 commits. The latest one is "iceland: Add Widevine OEMCrypto library" (19 Sep 2026).
- The repository has no build instructions, no CI workflow and no LICENSE file. It does not show whether it builds.
- Several source files carry an Apache-2.0 SPDX header, and one carries BSD-3-Clause-Clear. Check the header of each file.
- Issues are turned off for this repository. Report problems in [iceland-mainline](https://github.com/mzakamin-hub/iceland-mainline/issues).
