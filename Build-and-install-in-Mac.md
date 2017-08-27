Build from Qt Creator
=====================

1. Install [Homebrew](https://brew.sh/).
2. Intall the required dependencies: **brew install pkg-config qt5 caskroom/cask/qt-creator ffmpeg gstreamer gst-plugins-base pulseaudio jack libuvc**.
3. Open *Webcamoid.pro* file with Qt creator.
4. Go to **Projects** tab. 
5. In **Build**, in **Build environment** add */usr/local/bin* to *PATH* variable.
6. Then build and run.
