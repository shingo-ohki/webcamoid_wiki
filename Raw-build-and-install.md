Webcamoid's dependencies are:

* [Qt](https://qt-project.org/) (Qt >= 5)
* [FFmpeg](http://ffmpeg.org/) >= 2.0
* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x

You can build Webcamoid with the following commands:

    qmake-qt5 Webcamoid.pro
    make
    su -c 'make install'
