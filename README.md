**Unoficial Omnirom 4.3 for Sony Xperia Sola**

Getting Started :

    mkdir cm-10.2
    cd cm-10.2
    repo init -u git://github.com/tadeas482/manifest.git -b omni-4.3
    repo sync

Patch android source code :

    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_netd.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch

Our step is optional!!! Use only if you going to sync CM source code daily, than simple revert each patch before you sync CM source code :

    patch -p1 -R < device/sony/pepper/patches/framework_av.patch
    patch -p1 -R < device/sony/pepper/patches/framework_native.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 -R < device/sony/pepper/patches/system_netd.patch
    patch -p1 -R < device/sony/pepper/patches/system_core.patch
    repo forall -p -c 'git checkout -f'
    repo sync
    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_netd.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch

You are ready to build :

    . build/envsetup.sh
    lunch omni_pepper-userdebug
    make otapackage

ENJOY!
