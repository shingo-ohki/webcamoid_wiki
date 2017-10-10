First at all, you must install Qt from [here](http://qt-project.org/downloads).

Build from Qt Creator
=====================

1. Download FFmpeg from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/), you must download the **shared** and **dev** packages.
2. Extract the files, and put the **ffmpeg-#-shared/bin** folder, and the **ffmpeg-#-dev/include** and  **ffmpeg-#-dev/lib** in a common **ffmpeg** folder.
3. Open *Webcamoid.pro* file with Qt creator.
4. Go to **Projects** tab. 
5. In **Build**, in **Additional arguments** add *FFMPEGINCLUDES=C:\[path]\ffmpeg\include FFMPEGLIBS=-LC:\[path]\ffmpeg\lib FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavcodec FFMPEGLIBS+=-lswresample FFMPEGLIBS+=-lswscale FFMPEGLIBS+=-lavutil FFMPEGLIBS+=-lavdevice*
6. Copy all DLL from **ffmpeg-#-shared/bin** to the **webcamoid\StandAlone** folder.
7. In **Run**, in **Arguments** add *-r -q "%cd%\libAvKys" -p "%cd%\libAvKys\Plugins"*
8. Then build and run.
