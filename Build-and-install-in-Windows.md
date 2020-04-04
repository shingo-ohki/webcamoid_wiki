Please, read the [raw build guide](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install) and [deploy guide](https://github.com/webcamoid/webcamoid/wiki/Deploy-and-create-self-contained-binary-packages) before reading this guide, there you will find all available configurations to tweak the build.  

Notes
=====

When installing Qt from online or offline installer the **supported compilers are MSVC and MinGW**; UWP and Android compilers are not supported yet, unless you want to work in supporting them :wink:. You must also check **Qt Installer Framework** for deploy scripts.

Build from Qt Creator
=====================

1. Download FFmpeg from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/), you must download the **shared** and **dev** packages.
2. Extract the files, and put the **ffmpeg-#-shared/bin** folder, and the **ffmpeg-#-dev/include** and  **ffmpeg-#-dev/lib** in a common **ffmpeg** folder.
3. Open *Webcamoid.pro* file with Qt creator.
4. Go to **Projects** tab. 
5. In **Build**, in **Additional arguments** add:
  
```
FFMPEGINCLUDES=C:\[path]\ffmpeg\include FFMPEGLIBS=-LC:\[path]\ffmpeg\lib FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavcodec FFMPEGLIBS+=-lswresample FFMPEGLIBS+=-lswscale FFMPEGLIBS+=-lavutil FFMPEGLIBS+=-lavdevice
```
   
   **Note**: replace _[path]_ with the actual path.  
  
6. This step is optional but may be useful.  
    6.a) You can enable **Shadow build** to put all compiled and generated files in a different folder and leave source directory clean. In the **Build directory** write for example _C:\[path]\webcamoid-shadow_ to put compiled files there.  
    6.b) In **Additional arguments** you can add **CONFIG+=silent** to reduce compile verbosity, and make compile errors easier to notice.
    6.c) In **Build Steps > Make > Make arguments** add **-j[number of supported CPU threads]** to speed up build, for example **-j4**.  
7. This step is also optional but let you create the installer and portable packages. Enabling deploy scripts may slow down the build a lot, so you are advised to disable this if you are just debugging.  
    7.a) In **Build Steps > Add Build Step > Custom Process Step**, in **Command** add the path to **Python** interpreter, for example _C:\Program Files\Python\pythonw.exe_.  
    7.b) In **Argumments** add _C:\[path]\webcamoid\ports\deploy\deploy.py_.  
    7.c) You can disable this step checking the 🛇 icon near to **Details**.  
8. In **Build & Run > Run > Command line arguments** add:
  
```
-r -p C:\[path]\webcamoid\libAvKys\Plugins --vcam C:\[path]\webcamoid\libAvKys\Plugins\VirtualCamera\src\dshow\VirtualCamera
```
   
   **Note**: If you enabled **Shadow build** replace _C:\[path]\webcamoid_ with the shadow build folder.  
  
10. In **Run Environment** find **Path** variable and add _C:\[path]\ffmpeg\bin;_ at beginning.  
11. In the left bar, in :computer: on top of the run button, in the **Run** column select **StandAlone**.  
12. Build and run the project.
