# lrvick-rom #

<http://github.com/lrvick/android_manifest>

## About ##

This is an effort to produce a pure AOSP based rom for personal use, with a
simple goal to remain as open source as possible, save for vendor blobs
required to make basic hardware functions work.

Added bonus: I currently have no idea what I am doing!

## Features ##

  * Boots up. 
  * Wifi/bluetooth work.
  * Cellular radio does NOT work! (no idea why)

## Dependencies ##

 * Debian based distro ( Other distros use vm or debootstrap/chroot )
 * Debian packages:
			git-core gnupg flex bison gperf build-essential
  		zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386
  		lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev ccache
  		libgl1-mesa-dev libxml2-utils xsltproc unzip schedtool
 * [Repo Tool](http://github.com/lrvick/android_manifest)
 * [Android Platform Tools](https://developer.android.com/sdk/installing/index.html?pkg=tools)

## Building ##

```
> repo init -u https://github.com/lrvick/android_manifest -b master
> repo sync
> . build/envsetup.sh
> brunch angler
```
## Installation ##

```
> fastboot -w flashall
```

## Notes ##

Use at your own risk. You might be eaten by a grue.
