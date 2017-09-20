This page is for those who already have successfully compiled Webcamoid following the [build instructions](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install). Once Webcamoid compiled, you can create self-contained binary packages that contains all required dependencies for distribution or storage purpose.

## Type of packages supported ##

- **Portable**: This package is simply a compressed file containing a RBS (Raw Binary Structure) where you have direct access to all required dependencies (executable, libraries, plugins, etc.), this allow you to tweak Webcamoid, for example, removing plugins you don't need, adding new plugins, making tests and debug, and so on. This also serves as a package that can be carried between different computers.
- **Installable**: This package adds an installer GUI to the RBS, so you just need to follow the classic click-click-istall procedure to install Webcamoid on the computer. The package is designed to install Webcamoid in a fixed place, and modify the environment according to that place, integrating Webcamoid to it (creating shortcuts, menu entries, adding new icons, etc.).
- **AppImage**: Only available for GNU/Linux, this package contains the RBS but bundled inside a static ELF executable, this is a portable package, but unlike **Portable** package, this package is perceived and treated as an unique entity, and the AppImage protect and preserves the RBSs internal file permissions from file systems that doesn't support *nix file permissions (like FAT or NTFS). Also, the AppImage allow you to extract, modify and repack the RBS if you want.

## Supported build and target systems ##

- POSIX: This includes GNU/Linux, FreeBSD, and all POSIX compliant systems where you can compile Webcamoid. In GNU/Linux **Portable**, **Installable** and **AppImage** is available. In other systems only the **Portable** is available.
- POSIX to Windows: This requires MinGW and Wine to have installed in your system. This will create **Portable** and **Installable** packages for Windows.
- Windows: **Portable** and **Installable** packages are supported.
- Mac: **Portable** and **Installable** packages are supported.

## Dependencies ##

- [Python 3](https://www.python.org/)
- [Qt Installer Framework](http://download.qt.io/official_releases/qt-installer-framework/)
- [Mingw-w64](https://mingw-w64.org/doku.php)
- [Wine](https://www.winehq.org/)
- [appimagetool](https://github.com/AppImage/AppImageKit) (GNU/Linux only)

## Deploy ##

Creating the binary packages is as simple as executing the _ports/deploy/deploy.py_ located inside Webcamoid folder.

    python3 ports/deploy/deploy.py

**NOTE**: For GNU/Linux users, if you want to run the packages in newer and older distros, you must compile and create the packages in old enough systems, please read [here](https://github.com/AppImage/AppImageKit/wiki/Creating-AppImages#creating-portable-appimages) and [here](https://github.com/AppImage/AppImageKit/wiki/Desktop-Linux-Platform-Issues) for a very comprehensive guide.

## Platform notes ##

**In progress**

## Deploy flags ##

**In progress**