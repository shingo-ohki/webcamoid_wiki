Webcamoid's dependencies are:

* [Qt](https://qt-project.org/) (Qt >= 5.4, Qt5Base, Qt5Quick1, Qt5QuickControls)
* [FFmpeg](http://ffmpeg.org/) >= 2.8
* [GStreamer](http://gstreamer.freedesktop.org/) >= 1.6
* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x
* [libpulse](http://www.freedesktop.org/wiki/Software/PulseAudio)
* [v4l2loopback](https://github.com/umlaeute/v4l2loopback) (Optional for virtual camera support, not required for build)

Webcamoid by default uses **FFmpeg** as codec framework and it's the **recommended** one. You can build Webcamoid with the following commands:

    qmake-qt5 Webcamoid.pro
    make
    su -c 'make install'

Webcamoid also supports **GStreamer** as codec framework but its considered **experimental**. You can build Webcamoid with GStreamer support with the following commands:

    qmake-qt5 Webcamoid.pro USE_GSTREAMER
    make
    su -c 'make install'
