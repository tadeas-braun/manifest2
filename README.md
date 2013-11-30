**Unoficial Slim ROM 4.4(Android 4.4 KitKat) for Sony Xperia Sola**

Getting Started :

    mkdir slim-4.4
    cd slim-4.4
    repo init -u https://github.com/tadeas482/manifest.git -b slim-4.4
    repo sync

Patch android source code :

    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/framework_base.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch
    patch -p1 < device/sony/pepper/patches/system_netd.patch
    patch -p1 < device/sony/pepper/patches/bionic.patch

Our step is optional!!! Use only if you going to sync Slim source code daily, than simple revert each patch before you sync Slim source code :

    patch -p1 -R < device/sony/pepper/patches/framework_av.patch
    patch -p1 -R < device/sony/pepper/patches/framework_native.patch
    patch -p1 -R < device/sony/pepper/patches/framework_base.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 -R < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 -R < device/sony/pepper/patches/system_core.patch
    patch -p1 -R < device/sony/pepper/patches/system_netd.patch
    patch -p1 -R < device/sony/pepper/patches/bionic.patch
    repo forall -p -c 'git checkout -f'
    repo sync
    patch -p1 < device/sony/pepper/patches/framework_av.patch
    patch -p1 < device/sony/pepper/patches/framework_native.patch
    patch -p1 < device/sony/pepper/patches/framework_base.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware.patch
    patch -p1 < device/sony/pepper/patches/hardware_libhardware_legacy.patch
    patch -p1 < device/sony/pepper/patches/system_core.patch
    patch -p1 < device/sony/pepper/patches/system_netd.patch
    patch -p1 < device/sony/pepper/patches/bionic.patch

You are ready to build :

    . build/envsetup.sh
    lunch slim_pepper-userdebug
    make otapackage

ENJOY!
