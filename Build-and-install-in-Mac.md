Build from Qt Creator
=====================

1. Install [Homebrew](https://brew.sh/).
2. Intall the required dependencies: **brew install pkg-config qt5 ffmpeg gstreamer gst-plugins-base pulseaudio jack libuvc**.
3. Intall Qt Creator from homebrew (**brew install caskroom/cask/qt-creator**) or from [official releases](http://download.qt.io/official_releases/qtcreator/).
4. Open *Webcamoid.pro* file with Qt creator.
5. Go to **Projects** tab. 
6. In **Build**, in **Build environment** add */usr/local/bin* to *PATH* variable.
7. Then build and run.
