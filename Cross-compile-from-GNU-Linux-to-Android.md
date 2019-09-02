Please, read the [raw build guide](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install) and [deploy guide](https://github.com/webcamoid/webcamoid/wiki/Deploy-and-create-self-contained-binary-packages) before reading this guide, there you will find all available configurations to tweak the build.

**NOTE**: I will assume you already know how to install Qt, Qt Creator, Android SDK and Android NDK in your system.

### Installing dependencies ###

## Debian and Ubuntu

First at all install OpenJDK:

    sudo apt-get install make openjdk-8-jdk openjdk-8-jre

Then install the [Android SDK and NDK](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install#dependencies), and use the **sdkmanager** to install the base Android build dependencies:

    sdkmanager build-tools;28.0.3 platform-tools platforms;android-23 tools

You can choose whatever build tools and platform version you want, this is just an example.  
Since Debian and Ubuntu doesn't provides Qt's Android development packages you must install Qt from the [official downloads page](https://download.qt.io/official_releases/qt/), be sure to select the **android_arm64_v8a**, **android_armv7** and **android_x86** targets. 

## Arch

Install the following packages from the [AUR](https://aur.archlinux.org/):

    android-emulator android-environment android-ndk android-pkg-config android-platform android-sdk android-sdk-build-tools android-sdk-platform-tools android-aarch64-ffmpeg android-aarch64-qt5

Here **aarch64** and default **android-platform** is used as an example, feel free to install whatever architecture and platform you want.

**NOTE**: For both, Ubuntu and Arch, you must install the x86 or x86_64 packages for testing the APK in the emulator.

### Configuring Qt Creator ###

1. Open Qt Creator and go to menu _Tools > Options > Kits_.
2. Go to _Devices_. 
3. Configure **Android SDK location** and **Android NDK location** to where you installed the SDK and NDK. 
4. In _SDK Manager_ choose a platform, select and install the **SDK Platform** and the **Google APIs Intel x86 Atom_64 System Image**. 
5. In _ADV Manager_, go to _Add_, set a **Name**, select an **ABI**, select a **Target API**, and set a **SD card size** of 1024MiB as minimum.
6. Go to _Kits_. 
7. In **Qt Versions**, Press **Add** and select _/opt/android-libs/${ARCH}/bin/qmake_, and in **Version name** put **Qt %{Qt:Version} (${ARCH})**. Replace **${ARCH}** with the arch you want to build for (aarch64, armv7a-eabi, x86 or x86-64). Adjust the path to where you installed the Qt tools.
8. With Webcamoid project open, go to **Projects** tab.
9. Select the Android kit you configured just before.
10. Go to **Build Android APK**, in **Android build APK** select the platform you want to build for.
11. In **Build Environment**, set the variable **ANDROID_NDK_PLATFORM** to the platform you selected before.
12. Build and run the project.
