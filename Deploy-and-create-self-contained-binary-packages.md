This page is for those who already have successfully compiled Webcamoid following the [build instructions](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install). Once Webcamoid compiled, you can create self-contained binary packages that contains all required dependencies for distribution or storage purpose.

## Type of packages supported ##

- **Portable**: This package is simply a compressed file containing a RBS (Raw Binary Structure) where you have direct access to all required dependencies (executable, libraries, plugins, etc.), this allow you to tweak Webcamoid, for example, removing plugins you don't need, adding new plugins, making tests and debug, and so on. This also serves as a package that can be carried between different computers.
- **Installable**: This package adds an installer GUI to the RBS, so you just need to follow the classic click-click-istall procedure to install Webcamoid on the computer. The package is designed to install Webcamoid in a fixed place, and modify the environment according to that place, integrating Webcamoid to it (creating shortcuts, menu entries, adding new icons, etc.).
- **AppImage**: Only available for GNU/Linux, this package contains the RBS but bundled inside a static ELF executable, this is a portable package, but unlike **Portable** package, this package is perceived and treated as an unique entity, and the AppImage protect and preserves the RBSs internal file permissions from file systems that doesn't support *nix file permissions (like FAT or NTFS). Also, the AppImage allow you to extract, modify and repack the RBS if you want.
- **Android APK**: Only available for Android targets. This produces an APK ready to use in Android.

## Supported build and target systems ##

- POSIX: This includes GNU/Linux, FreeBSD, and all POSIX compliant systems where you can compile Webcamoid. In GNU/Linux **Portable**, **Installable** and **AppImage** is available. In other systems only the **Portable** is available.
- POSIX to Windows: This requires MinGW and Wine to have installed in your system. This will create **Portable** and **Installable** packages for Windows.
- Windows: **Portable** and **Installable** packages are supported.
- Mac: **Portable** and **Installable** packages are supported.
- Android: Only the **APK** build is supported.

## Dependencies ##

- [Python 3](https://www.python.org/)
- [Qt Installer Framework](http://download.qt.io/official_releases/qt-installer-framework/)
- [Mingw-w64](https://mingw-w64.org/doku.php)
- [Wine](https://www.winehq.org/)
- [appimagetool](https://github.com/AppImage/AppImageKit) (GNU/Linux only)

## Deploy ##

Creating the binary packages is as simple as executing the _ports/deploy/deploy.py_ located inside Webcamoid folder.

    python3 ports/deploy/deploy.py

## Platform notes ##

For GNU/Linux users, if you want to run the packages in newer and older distros, you must compile and create the packages in old enough systems, please read [here](https://github.com/AppImage/AppImageKit/wiki/Creating-AppImages#creating-portable-appimages) and [here](https://github.com/AppImage/AppImageKit/wiki/Desktop-Linux-Platform-Issues) for a very comprehensive guide.  
From POSIX to Windows deploy, the deploy script will search for dependencies in the same directory where Qt is installed, following **qmake -query** directives.  
For Mac users, the deploy script may be able to work with both official Qt releases and Homebrew.  
For Window users, the deploy script may be able to work with both official Qt releases and MSYS2.  
The Android APK build has only be tested in GNU/Linux host, it may work in other operating system with a few modifications.

## Deploy flags ##

Following environment variables are supported:

### Global flags ###

- **PATH**: List of colon or semi-colon (Windows) separated list of paths to search for binaries. System wide environment variable.
- **QMAKE_PATH**: Path to Qmake executable.
- **BINARYCREATOR**: Path to Qt Installer framework's binarycreator executable.

### POSIX ###

- **LD_LIBRARY_PATH**: List of colon separated list of paths to search for libraries. System wide environment variable.
- **APPIMAGETOOL**: Path to AppImage's imagetool executable.

### Mac ###

- **DYLD_LIBRARY_PATH**: List of colon separated list of paths to search for libraries. System wide environment variable.
- **DYLD_FRAMEWORK_PATH**: List of colon separated list of paths to search for Frameworks. System wide environment variable.

### Windows ###

- **MAKE_PATH**: Path to make executable.
- **INSTALL_PREFIX**: Path where binary files will be installed when running _make install_.

### Android ###

- **KEYSTORE_PATH**: Indicate where is located the keystore file used to sign the APK.
- **PACKAGES_PREPARE_ONLY**: when this variable is set to **1* won't create the APK,instead it will only solve the CPU architecture dependent libraries so it can be later used in package merging.
- **PACKAGES_MERGE**: Colon separated list of build paths that will be used to scan the CPU architecture dependent libraries so it can be copied to the current package. The resulting APK will be able to run in all targets supported by those architectures.
