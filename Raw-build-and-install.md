Webcamoid's dependencies are:

* [Qt](https://qt-project.org/) (Qt >= 5.5, Qt5Base, Qt5Quick1, Qt5QuickControls)
* [FFmpeg](http://ffmpeg.org/) >= 2.8
* [GStreamer](http://gstreamer.freedesktop.org/) >= 1.6
* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x
* [libpulse](http://www.freedesktop.org/wiki/Software/PulseAudio)
* [v4l2loopback](https://github.com/umlaeute/v4l2loopback) (Optional for virtual camera support, not required for build)
* [Mingw-w64](http://mingw-w64.org/doku.php) (>= 5.3.0 for virtual camera support, older versions supported with *COMPILE_VCAM_DRIVER=0*) **Windows**

Webcamoid by default uses **FFmpeg** as codec framework and it's the **recommended** one. You can build Webcamoid with the following commands:

    qmake-qt5 Webcamoid.pro # BUILD_FLAGS ...
    make
    su -c 'make install'

## Build flags ##

### Build options ###

- **USE_GSTREAMER**: Use GStreamer instead of FFmpeg as codec framework (options: 0, 1; default: 0) **EXPERIMENTAL**
- **BUILDDOCS**: Build documentation files (options: 0, 1; default: 0)
- **INSTALLDEVHEADERS**: Install development headers (options: 0, 1; default: 0) **UNSTABLE**
- **STATIC_BUILD**: Build Webcamoid statically (options: 0, 1; default: 0)
- **COMPILE_VCAM_DRIVER**: Compile virtual camera driver (options: 0, 1; default: 1) **Windows only**
- **ROOT_METHOD**: Select the preferred method for running commands that requires root access (options: su, sudo; default: su) **GNU/Linux only**

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
- **LOCALEDIR**: Translations files (*DATAROOTDIR/locale*)
- **MANDIR**: Man documentation (*DATAROOTDIR/man*)
- **LICENSEDIR**: License files (*DATAROOTDIR/licenses/webcamoid*)
