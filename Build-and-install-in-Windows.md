First at all, you must install Qt from [here](http://qt-project.org/downloads). You will also need to download the files **D3DCompiler_43.dll**, **D3DCompiler_46.dll** and **D3DCompiler_47.dll** from some DLL download page.

Build from Qt Creator
=====================

1. Download FFmpeg 2.8 or higher from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/), you must download the **shared** and **dev** packages.
2. Extract the files, and put the **ffmpeg-#-shared/bin** folder, and the **ffmpeg-#-dev/include** and  **ffmpeg-#-dev/lib** in a common **ffmpeg** folder.
3. Open *Webcamoid.pro* file with Qt creator.
4. Go to **Projects** tab. 
5. In **Build**, in **Additional arguments** add *FFMPEGINCLUDES=C:\[path]\ffmpeg\include FFMPEGLIBS=-LC:\[path]\ffmpeg\lib FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavcodec FFMPEGLIBS+=-lswresample FFMPEGLIBS+=-lswscale FFMPEGLIBS+=-lavutil FFMPEGLIBS+=-lavdevice*
5. Copy all DLL from **ffmpeg-#-shared/bin** and all **D3DCompiler_#.dll** to the **webcamoid\StandAlone** folder.
6. In **Run**, in **Arguments** add *-r -q "%cd%\libAvKys" -p "%cd%\libAvKys\Plugins"*
7. Then build and run.

Build with MSYS
===============

1. Install MSYS from [here](http://downloads.sourceforge.net/mingw/MSYS-1.0.11.exe).
2. Edit the _C:\MinGW\msys\1.0\etc\fstab_ file and write some shortcuts:

        #Win32_Path                        Mount_Point
        C:\MinGW                           /mingw
        C:\Users\YourUser\Documents        /documents
        C:\Users\YourUser\Desktop          /desktop
        C:\Qt\5.5.1\5.5\mingw492_32\bin    /qttools

3. Open the MSYS console and install the build system:

        mingw-get install mingw-developer-toolkit mingw-base mingw-gcc-g++ msys-base msys-unzip  msys-wget msys-w32api

4. In the MSYS console move to the _Webcamoid/ports/msys_ folder.

        cd /documents/Webcamoid-7.0.0/ports/msys

5. Execute the build script:

        ./build.sh

More info [here](http://mingw.org/wiki/msys) and [here](http://mingw.org/wiki/Getting_Started).
