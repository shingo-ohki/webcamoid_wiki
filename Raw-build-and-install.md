Webcamoid's dependencies are:

* [Qt](https://qt-project.org/) (Qt >= 4.7 and Qt5)
* [kdelibs](https://projects.kde.org/projects/kde/kdelibs)
* [OpenCV](http://opencv.org/) >= 2.0
* [FFmpeg](http://ffmpeg.org/) >= 2.0
* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x

Build dependecies:

* [Bison](http://www.gnu.org/software/bison/bison.html) >= 2.5
* [Flex](http://flex.sourceforge.net)

You can build Webcamoid with the following commands:

    qmake-qt4 Webcamoid.pro
    make
    su -c 'make INSTALL_ROOT=/usr install'
    kbuildsycoca4
