Webcamoid's dependencies are:

* [Qt](https://qt-project.org/) (Qt >= 4.7 and Qt5)
* [kdelibs](https://projects.kde.org/projects/kde/kdelibs)
* [Frei0r plugins](http://www.piksel.org/frei0r)
* [FFmpeg](http://ffmpeg.org/) >= 2.0
* [linux-api-headers](http://www.gnu.org/software/libc) >= 3.6.x

**NOTE**: Some distributions doesn't provides FFmpeg packages, if this is your case, enable the **USE3DPARTYLIBS** options in QMake.

Build dependecies:

* [Wget](http://www.gnu.org/software/wget/wget.html) (if **USE3DPARTYLIBS** is enabled)
* [Bison](http://www.gnu.org/software/bison/bison.html) >= 2.5
* [Flex](http://flex.sourceforge.net)

You can build Webcamoid with the following commands:

    qmake-qt4 Webcamoid.pro #USE3DPARTYLIBS=1
    make
    su -c 'make INSTALL_ROOT=/usr install'
    kbuildsycoca4
