# android_device_realme_RMX2117
For building TWRP for realme Narzo 30 Pro 5g

## Features

Works:

- ADB
- Decryption of /data (without password)
- Screen brightness settings
- Vibration on touch

# Compile

#First checkout minimal twrp with omnirom tree:

```
repo init --depth=1 -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11 --groups=all,-notdefault,-device,-darwin,-x86,-mips

repo sync

|or|

repo sync --force-sync --no-clone-bundle --no-tags -j$(nproc --all)
```

#Finally execute these:

```
export ALLOW_MISSING_DEPENDENCIES=true
. build/envsetup.sh
lunch twrp_RMX2117-eng
mka -j$(nproc --all) recoveryimage

|or|

export ALLOW_MISSING_DEPENDENCIES=true; source build/envsetup.sh; lunch twrp_RMX2117-eng; mka -j$(nproc --all) recoveryimage
```
