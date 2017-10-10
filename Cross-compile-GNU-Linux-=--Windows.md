This page explain how to setup your build environment if you want to compile Webcamoid for Windows or Wine while working in GNU/Linux.

**NOTE 1:** These instructions are focused in Arch Linux since I did not found an equivalent setup for other distros.  
**NOTE 2:** I will assume you already have installed Qt and Qt Creator in your system.

## Installing dependencies ##

Webcamoid uses Martchus' Qt packages for building binaries for Windows, you can find them in AUR or precompiled, [see here](https://github.com/Martchus/PKGBUILDs) for more information. You can install all required dependencies with:

    yaourt -S wine mingw-w64 mingw-w64-qt5-base-dynamic mingw-w64-qt5-quickcontrols mingw-w64-qt5-svg

You also must download the FFmpeg packages from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/) (FFmpeg from AUR will not work in Windows), you need **shared** (provide DLLs) and **dev** (provide headers and libs) packages. The recommended file layout for FFmpeg is as follow:

    webcamoid/project_priv/win32/ffmpeg/bin
    webcamoid/project_priv/win32/ffmpeg/include
    webcamoid/project_priv/win32/ffmpeg/lib

And for 64 bits:

    webcamoid/project_priv/win64/ffmpeg/bin
    webcamoid/project_priv/win64/ffmpeg/include
    webcamoid/project_priv/win64/ffmpeg/lib

You can put FFmpeg packages outside of Webcamoid folder if you want, but remember to adjust your environment according to that.

## Configuring Qt Creator ##

**In Progress**
