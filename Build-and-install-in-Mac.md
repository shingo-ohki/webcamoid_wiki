Please, read the [raw build guide](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install) and [deploy guide](https://github.com/webcamoid/webcamoid/wiki/Deploy-and-create-self-contained-binary-packages) before reading this guide, there you will find all available configurations to tweak the build.  

Build from Qt Creator
=====================

1. Install [Homebrew](https://brew.sh/).
2. Install the required [dependencies](https://github.com/webcamoid/webcamoid/blob/master/ports/ci/travis/install_deps.sh#L479).
3. Intall Qt Creator from homebrew (**brew install caskroom/cask/qt-creator**) or from [official releases](http://download.qt.io/official_releases/qtcreator/).
4. Open *Webcamoid.pro* file with Qt creator.
5. If this is the first time you used Qt Creator, you probably have not any kit configured to build the project, so go to **Qt Creator > Preferences... > Build & Run > Qt Versions > Add** press ⇧⌘G and write _/usr/local/Cellar/qt_, go into the folder of the Qt version you have installed, then select bin/qmake.
6. Now go to **Kits**, select the **Desktop kit**, and then configure as follow:
   
   **Device type**: Desktop  
   **Compiler C/C++**: Clang (x86 64 bit in /usr/bin)  
   **Debugger**: System LLDB at /usr/bin/lldb  
   **Qt version**: the Qt version you configured just before  
7. Go to **General**, in **Default build directory** write **.** (a point), **Ok** and close the window.
8. Now in **Configure Project** page that appears when you opened the project, select the kit you configured, check **Debug**, **Release** and **Profile**, and **Configure project** button.
9. Go to **Projects** tab.
10. In **General**, uncheck **Shadow build**, it doesn't seems to play well in Mac.
11. This step is optional but may be useful.  
    11.a) In **Additional arguments** you can add **CONFIG+=silent** to reduce compile verbosity, and make compile errors easier to notice.
    11.b) In **Build Steps > Make > Make arguments** add **-j[number of supported CPU threads]** to speed up build, for example **-j4**.  
12. This step is also optional but let you create the installer and portable packages. Enabling deploy scripts may slow down the build a lot, so you are advised to disable this if you are just debugging.  
    12.a) In **Build Steps > Add Build Step > Custom Process Step**, in **Command** write **python3**.  
    12.b) In **Arguments** add _/[path]/webcamoid/ports/deploy/deploy.py_.  
    12.c) You can disable this step checking the 🛇 icon near to **Details**.  
13. In **Build & Run > Run > Command line arguments** add:
  
```
--vcam /[path]/webcamoid/libAvKys/Plugins/VirtualCamera/src/cmio/VirtualCamera -r -p /[path]/webcamoid/libAvKys/Plugins -q /[path]/webcamoid/libAvKys
```
   
   **Note**: Replace _/[path]_ with the folder where is Webcamoid source code.  
  
14. In **Build**, in **Build environment** add */usr/local/bin* to *PATH* variable.
15. In the left bar, in :computer: on top of the run button, in the **Run** column select **StandAlone**.  
16. Build and run the project.
