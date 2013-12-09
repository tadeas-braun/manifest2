**Unoficial AOSP 4.4.1 for Sony Xperia Sola**

Getting Started :

    mkdir aosp-4.4
    cd aosp-4.4
    repo init -u https://github.com/tadeas482/manifest.git -b aosp-4.4
    repo sync

Patch android source code :

    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/framework_base.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch
    patch -p1 < device/sony/pepper/patches/bionic.patch
    patch -p1 < device/sony/pepper/patches/bootable_recovery.patch
    patch -p1 < device/sony/pepper/patches/external_bluetooth_bluedroid.patch

Our step is optional!!! Use only if you going to sync AOSP source code daily, than simple revert each patch before you sync AOSP source code :

    patch -p1 -R < device/sony/pepper/patches/framework_av.patch
    patch -p1 -R < device/sony/pepper/patches/framework_native.patch
    patch -p1 -R < device/sony/pepper/patches/framework_base.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 -R < device/sony/pepper/patches/system_core.patch
    patch -p1 -R < device/sony/pepper/patches/bionic.patch
    patch -p1 -R < device/sony/pepper/patches/bootable_recovery.patch
    patch -p1 -R < device/sony/pepper/patches/external_bluetooth_bluedroid.patch
    repo forall -p -c 'git checkout -f'
    repo sync
    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/framework_base.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch
    patch -p1 < device/sony/pepper/patches/bionic.patch
    patch -p1 < device/sony/pepper/patches/bootable_recovery.patch
    patch -p1 < device/sony/pepper/patches/external_bluetooth_bluedroid.patch

You are ready to build :

    . build/envsetup.sh
    lunch full_pepper-userdebug
    make otapackage

ENJOY!
