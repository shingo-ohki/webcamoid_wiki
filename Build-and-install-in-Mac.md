Build from Qt Creator
=====================

1. Install [Homebrew](https://brew.sh/).
2. Install the required dependencies:  
   
   **Basic**: _brew install pkg-config qt5 ffmpeg_  
   **Full**: _brew install pkg-config qt5 ffmpeg gstreamer gst-plugins-base pulseaudio jack libuvc_
3. Intall Qt Creator from homebrew (**brew install caskroom/cask/qt-creator**) or from [official releases](http://download.qt.io/official_releases/qtcreator/).
4. Open *Webcamoid.pro* file with Qt creator.
5. If this is the first time you used Qt Creator, you probably have not any kit configured to build the project, so go to _Qt Creator > Preferences... > Build & Run > Qt Versions > Add_ press ⇧⌘G and write /usr/local/Cellar/qt, go into the folder of the Qt version you have installed, then select bin/qmake.
6. Now go to **Kits**, select the **Desktop kit**, and then configure as follow:
   
   **Device type**: Desktop  
   **Compiler C/C++**: Clang (x86 64 bit in /usr/bin)  
   **Debugger**: System LLDB at /usr/bin/lldb  
   **Qt version**: the Qt version you configured just before  
7. Go to **General**, in **Default build directory** write **.** (a point), **Ok** and close the window.
8. Now in **Configure Project** page that appears when you opened the project, select the kit you configured, check **Debug**, **Release** and **Profile**, and **Configure project** button.
9. Go to **Projects** tab. 
10. In **Build**, in **Build environment** add */usr/local/bin* to *PATH* variable.
11. Then build and run.
