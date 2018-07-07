## Dependencies ##

The main Webcamoid's dependency is Qt, and it can compile without any other dependency although you will miss a lot of features and will probably not work at all. Webcamoid can detect which development libraries you have installed in your system and enable support in build according to it, then you will be able to select which library you want to use at run-time for each task.

* [Qt](https://qt-project.org/) (Qt >= 5.9.0, QtBase, QtDeclarative, QtQuickControls 1, QtQuickControls 2, QtSvg)

The following are operating system targeting dependencies.

**GNU/Linux**

* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x
* [v4l2loopback](https://github.com/umlaeute/v4l2loopback) (Optional for virtual camera support, not required for build)

**Mac**

* Xcode Command Line Tools (_xcode-select --install_ from a terminal)

**Windows**

* [Mingw-w64](http://mingw-w64.org/doku.php) >= 4.9.2 (>= 5.3.0 for virtual camera support)
* [Build Tools for Visual Studio](https://www.visualstudio.com/downloads) >= 2015

You need at least one library for each category.

**Codec frameworks**

* [FFmpeg](http://ffmpeg.org/) >= 2.8 (*recommended*)
* [Libav](https://libav.org/) >= 9.20
* [GStreamer](http://gstreamer.freedesktop.org/) >= 1.6

**Audio playback**

* [libpulse](http://www.freedesktop.org/wiki/Software/PulseAudio) (*recommended*)
* [ALSA](http://www.alsa-project.org/main/index.php/Main_Page)
* [JACK Audio Connection Kit](http://www.jackaudio.org/)
* [QtMultimedia](http://doc.qt.io/qt-5/qtmultimedia-index.html)

**Video capture**

This libraries are optional but extends functionalities for video capture.

* [V4l-utils](https://www.linuxtv.org/wiki/index.php/V4l-utils) (extra formats for the webcam)
* [libuvc](https://github.com/ktossell/libuvc) (webcam support independent from operating system, **BUGGY**)

**Virtual camera management (GNU/Linux only)**

These programs allow user to add and remove the virtual webcam from the UI. These programs are not required for build.

* [kdesu](https://www.kde.org/workspaces/plasmadesktop/) (*recommended*)
* [gksu](http://www.nongnu.org/gksu/index.html)
* [kdesudo](https://launchpad.net/kdesudo)
* [gtksu](https://github.com/KeithDHedger/GtkSu)
* [sudo](https://www.sudo.ws/sudo/)

## Build and install ##

You can build Webcamoid with the following commands:

    qmake-qt5 Webcamoid.pro BUILD_FLAGS_GOES_HERE
    make
    su -c 'make install'

## Build flags ##

### General build options ###

- **BUILDDOCS=1**: Build documentation files **STUB**
- **INSTALLDEVHEADERS=1**: Install development headers **API IS UNSTABLE**
- **STATIC_BUILD=1**: Build Webcamoid statically **EXPERIMENTAL**

### Disable features ###

Webcamoid has a modular design, if you disable some feature during build you can build it later without rebuilding the entire project again, just building the required submodule.

- **NOALSA=1**: Disable ALSA support at build
- **NOAVFOUNDATION=1**: Disable AVFoundation support at build
- **NOCOREAUDIO=1**: Disable CoreAudio support at build
- **NOCOREMEDIAIO=1**: Disable Mac virtual camera support at build
- **NODSHOW=1**: Disable DirectShow support at build
- **NOFFMPEG=1**: Disable FFmpeg support at build
- **NOGSTREAMER=1**: Disable GStreamer support at build
- **NOJACK=1**: Disable JACK support at build
- **NOLIBUVC=1**: Disable libuvc support at build
- **NOMEDIAFOUNDATION=1**: Disable Microsoft Media Foundation support at build
- **NOOSS=1**: Disable OSS support at build
- **NOPULSEAUDIO=1**: Disable PulseAudio support at build
- **NOQTAUDIO=1**: Disable QAudio support at build
- **NOV4L2=1**: Disable V4L2 support at build
- **NOV4LUTILS=1**: Disable V4L-utils support at build
- **NOWASAPI=1**: Disable WASAPI support at build
- **NOVCAMWIN=1**: No build virtual camera in Windows
- **NOVIDEOEFFECTS=1**: No build video effects
- **NOLRELEASE=1**: No rebuild translations
- **VIRTUALCAMERAONLY=1**: Only build virtual camera components. This option is used with _webcamoid/libAvKys/Plugins/VirtualCamera/VirtualCamera.pro_, no other parts are required to build if you enabled this option.

### Install paths ###

- **PREFIX**: Architecture-independent files (linux: */usr*, windows: *C:\\Program Files\Webcamoid*)
- **EXECPREFIX**: Architecture-dependent files (*PREFIX*)
- **BINDIR**: User executables (*EXECPREFIX/bin*)
- **SBINDIR**: System admin executables (*EXECPREFIX/sbin*)
- **LIBEXECDIR**: Program executables (*EXECPREFIX/libexec*)
- **DATAROOTDIR**: Canonincal read-only architecture-independent data (*PREFIX/share*)
- **DATDIR**: Read-only architecture-independent data (*DATAROOTDIR/webcamoid*)
- **SYSCONFDIR**: Read-only single-machine data (*PREFIX/etc*)
- **SHAREDSTATEDIR**: Modifiable architecture-independent data (*PREFIX/com*)
- **LOCALSTATEDIR**: Modifiable single-machine data (*PREFIX/var*)
- **INCLUDEDIR**: C header files (*PREFIX/include*)
- **DOCDIR**: Documentation files (*DATAROOTDIR/doc/webcamoid*)
- **LIBDIR**: Object code libraries (*EXECPREFIX/lib*)
- **INSTALLQMLDIR**: Path where Qml files will be installed (*LIBDIR/qt/qml*)
- **LOCALEDIR**: Translations files (*DATAROOTDIR/locale*)
- **MANDIR**: Man documentation (*DATAROOTDIR/man*)
- **LICENSEDIR**: License files (*DATAROOTDIR/licenses/webcamoid*)

### Controlling libraries and frameworks paths ###

You can control the paths where Qmake will search for libraries and frameworks by passing the required variables to it. 

__INCLUDES__ variables points to the path where header files are located.

__LIBS__ variables controls the way the linker will link a binary file to a library or framework. Setting __LIBS__ disables pkg-config auto-detection.

Following is the table with available variables for each library:

<table>
    <thead>
        <tr><th>LibraryFramework</th><th>Headers</th><th>Libraries</th><th>Example</th></tr>
    </thead>
    <tbody>
        <tr>
            <td>FFmpeg</td><td>FFMPEGINCLUDES</td><td>FFMPEGLIBS</td>
            <td>
                FFMPEGINCLUDES=/opt/ffmpeg/include
                <br />
                <br />
                FFMPEGLIBS=-L/opt/ffmpeg/lib FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavcodec
            </td>
        </tr>
        <tr>
            <td>GStreamer</td><td>GSTREAMERINCLUDES</td><td>GSTREAMERLIBS</td>
            <td>
                GSTREAMERINCLUDES=/opt/gstreamer/include
                <br />
                <br />
                GSTREAMERLIBS=-L/opt/gstreamer/lib GSTREAMERLIBS+=-lgstaudio GSTREAMERLIBS+=-lgstvideo
            </td>
        </tr>
        <tr>
            <td>libusb</td><td>LIBUSBINCLUDES</td><td>LIBUSBLIBS</td>
            <td>
                LIBUSBINCLUDES=/opt/libusb/include
                <br />
                <br />
                LIBUSBLIBS=-L/opt/libusb/lib LIBUSBLIBS+=-lusb
            </td>
        </tr>
        <tr>
            <td>libuvc</td><td>LIBUVCINCLUDES</td><td>LIBUVCLIBS</td>
            <td>
                LIBUVCINCLUDES=/opt/libuvc/include
                <br />
                <br />
                LIBUVCLIBS=-L/opt/libuvc/lib LIBUVCLIBS+=-luvc
            </td>
        </tr>
    </tbody>
</table>
