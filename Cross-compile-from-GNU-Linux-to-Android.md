Please, read the [raw build guide](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install) and [deploy guide](https://github.com/webcamoid/webcamoid/wiki/Deploy-and-create-self-contained-binary-packages) before reading this guide, there you will find all available configurations to tweak the build.

**NOTE**: I will assume you already know how to install Qt, Qt Creator, Android SDK and Android NDK in your system.

### Installing dependencies ###

## Ubuntu

First at all install OpenJDK:

    sudo apt-get install make openjdk-8-jdk openjdk-8-jre

Then install the [Android SDK and NDK](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install#dependencies), and use the **sdkmanager** to install the base Android build dependencies:

    sdkmanager build-tools;28.0.3 platform-tools platforms;android-23 tools

You can choose whatever build tools and platform version you want, this is just an example.  
Now install Qt from the [official downloads page](https://download.qt.io/official_releases/qt/), be sure to select the **android_arm64_v8a**, **android_armv7** and **android_x86** targets. 

## Arch

Install the following packages from the [AUR](https://aur.archlinux.org/):

    android-emulator android-environment android-ndk android-pkg-config android-platform android-sdk android-sdk-build-tools android-sdk-platform-tools android-aarch64-ffmpeg android-aarch64-qt5

Here **aarch64** is used as an example, feel free to install whatever platform architecture and version you want.

### Configuring Qt Creator ###

**In progress**
