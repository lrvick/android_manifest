# lrvick-rom #

<http://github.com/lrvick/android_manifest>

## About ##

This is an effort to produce a pure AOSP based ROM for the Nexus 6P with the
simple goals of remaining as open source and as close to AOSP as possible.

If anyone ever actually cares about this, the project might get a real name
or support for other phones. Until such time this project exists with only my
personal use in mind, and as a reference for others wanting to do similar.

## Features ##

  * Minimal changes from AOSP.
  * Google Fi LTE, Bluetooth, Wifi all work as expected
  * No security shortcuts like disabling SELinux.
  * Google Apps and Play Services are -optional-
  * Vendor blobs auto-extracted direct from Google Servers
  * Built-in Superuser and Busybox

## Google Apps Alternatives ##

  If you, choose to opt out of Google Apps and use the ROM as-is, consider
  the following open alternatives I use daily:

  * Play Store -> F-Droid
  * Chrome -> Firefox
  * Google Music -> Tomahawk
  * Google Maps -> Maps.me
  * Youtube -> Newpipe
  * Hangouts -> Weechat - (IRC/XMPP but no Hangouts. Google shut down the APIs)

## Dependencies ##

 * Debian based distro ( Other distros use vm or debootstrap/chroot )
 * Debian packages:
			git-core gnupg flex bison gperf build-essential
  		zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386
  		lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache
  		libgl1-mesa-dev libxml2-utils xsltproc unzip schedtool
 * [Repo Tool](https://source.android.com/source/downloading.html#installing-repo)
 * [Android Platform Tools](https://developer.android.com/sdk/installing/index.html?pkg=tools)

## Building ##

Sync Sources:
```
> repo init -u https://github.com/lrvick/android_manifest -b master
> repo sync
```

Set up Environmet:
```
> . build/envsetup.sh
> export CROSS_COMPILE=aarch64-linux-android-
```

Build Kernel:
```
> cd kernel/huawei/angler/
> make angler_defconfig
> make -j4
```

Build ROM:
```
> lunch aosp_angler-userdebug
> bash device/huawei/angler/extract-files.sh
> make -j4
```

## Installation ##

Reboot into Fastboot mode.

```
> fastboot -w flashall
```

## Notes ##

Use at your own risk. You might be eaten by a grue.
