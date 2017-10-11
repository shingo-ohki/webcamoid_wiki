This page explain how to setup your build environment if you want to compile Webcamoid for Windows or Wine while working in GNU/Linux.

**NOTE 1:** These instructions are focused in Arch Linux since I did not found an equivalent setup for other distros.  
**NOTE 2:** I will assume you already have installed Qt and Qt Creator in your system.

## Installing dependencies ##

Webcamoid uses Martchus' Qt packages for building binaries for Windows, you can find them in AUR or precompiled, [see here](https://github.com/Martchus/PKGBUILDs) for more information. You can install all required dependencies with:

    yaourt -S wine mingw-w64 mingw-w64-qt5-base-dynamic mingw-w64-qt5-quickcontrols mingw-w64-qt5-svg

You also must download the FFmpeg packages from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/) (FFmpeg from AUR is broken and does not work in Windows), you need **shared** (provide DLLs) and **dev** (provide headers and libs) packages. The recommended file layout for FFmpeg is as follow:

    webcamoid/project_priv/win32/ffmpeg/bin
    webcamoid/project_priv/win32/ffmpeg/include
    webcamoid/project_priv/win32/ffmpeg/lib

And for 64 bits:

    webcamoid/project_priv/win64/ffmpeg/bin
    webcamoid/project_priv/win64/ffmpeg/include
    webcamoid/project_priv/win64/ffmpeg/lib

You can put FFmpeg packages outside of Webcamoid folder if you want, but remember to adjust your environment according to that.

## Configuring Qt Creator ##

1. Open Qt Creator and go to menu _Tools > Options > Build & Run_.
2. In **Qt Versions**, Press **Add** and select _/usr/i686-w64-mingw32/lib/qt/bin/qmake_ and _/usr/x86_64-w64-mingw32/lib/qt/bin/qmake_, and in **Version name** put **Qt %{Qt:Version} in PATH (lib, MinGW i686)** and **Qt %{Qt:Version} in PATH (lib, MinGW x86_64)** respectively.
3. In **Compilers**,  Press **Add MinGW** and select 

   C++: _/usr/bin/i686-w64-mingw32-g++_ and _/usr/bin/x86_64-w64-mingw32-g++_  
   C: _/usr/bin/i686-w64-mingw32-gcc_ and _/usr/bin/x86_64-w64-mingw32-gcc_  
4. In **Debuggers**, Press **Add** and select _/usr/bin/i686-w64-mingw32-gdb_ and  _/usr/bin/x86_64-w64-mingw32-gdb_.
5. In **Kits**, Press **Add** and fill the fields as:
  
   **Name**: Desktop Qt %{Qt:Version} %{Compiler:Name}  
   **Device type**: Desktop  
   **Compiler C/C++**: MinGW  
   **Debugger**: MinGW GDB  
   **Qt version**: the MinGW Qt version you configured just before  
6. With Webcamoid project open, go to **Projects** tab.
7. Select the MinGW kit you configured just before.
8. In _Build > Build Steps > Additional arguments_, write  

   PREFIX=/webcamoid FFMPEGINCLUDES=project_priv/win32/ffmpeg/include FFMPEGLIBS=-Lproject_priv/win32/ffmpeg/lib FFMPEGLIBS+=-lavcodec FFMPEGLIBS+=-lavdevice FFMPEGLIBS+=-lavfilter FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavutil FFMPEGLIBS+=-lpostproc FFMPEGLIBS+=-lswresample FFMPEGLIBS+=-lswscale.

   Adjust the paths according to the paths of FFmpeg packages.

## Running Webcamoid in Wine ##

Now you must create a _webcamoid/project_priv/win32/webcamoid.bat_ file so you can launch Webcamoid in Wine from Qt Creator, the contents of the launcher is as follow:

    SET PATH=%cd%\libAvKys\Lib;%cd%\project_priv\win32;%cd%\project_priv\win32\ffmpeg\bin;Z:\usr\i686-w64-mingw32\bin;%PATH%
    StandAlone\webcamoid -r -q "%cd%\libAvKys" -p "%cd%\libAvKys\Plugins" -c "%cd%\project_priv\config"

    pause

Then in Qt Creator:

1. Go to _Projects > Run > Run Settings_.
2. In **Run configuration** press _Add > Custom Executable_, and fill the fields as:  
   
   **Executable**: wineconsole  
   **Command line argumments**: _project_priv/win32/webcamoid.bat_  
   **Working directory**: %{buildDir}

Then you will be ready to build, launch and test Webcamoid in MinGW and Wine.
