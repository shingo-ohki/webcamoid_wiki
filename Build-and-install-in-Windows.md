First at all, you must install Qt from [here](http://qt-project.org/downloads).

Build from Qt Creator
=====================

1. Download FFmpeg from [Zeranoe builds](https://ffmpeg.zeranoe.com/builds/), you must download the **shared** and **dev** packages.
2. Extract the files, and put the **ffmpeg-#-shared/bin** folder, and the **ffmpeg-#-dev/include** and  **ffmpeg-#-dev/lib** in a common **ffmpeg** folder.
3. Open *Webcamoid.pro* file with Qt creator.
4. Go to **Projects** tab. 
5. In **Build**, in **Additional arguments** add *FFMPEGINCLUDES=C:\[path]\ffmpeg\include FFMPEGLIBS=-LC:\[path]\ffmpeg\lib FFMPEGLIBS+=-lavformat FFMPEGLIBS+=-lavcodec FFMPEGLIBS+=-lswresample FFMPEGLIBS+=-lswscale FFMPEGLIBS+=-lavutil FFMPEGLIBS+=-lavdevice*
6. In **Build** add an additional Build step:  
Command: xcopy  
Arguments: /y ..\webcamoid\libAvKys\AkQml\qmldir %{buildDir}\libAvKys\AkQml\  
Working Directory: %{buildDir}  
Note! this is assuming you cloned the project in a folder named webcamoid and do a shadow build thats parallel to the checkout folder. this is the default when you just clone and open the project.  
7. Build the project
8. Copy all DLL from **ffmpeg-#-shared/bin** to the **StandAlone** folder inside your build folder.
9. In **Run**, in **Arguments** add *-r -q "{replace with absolute path to the build folder}\libAvKys" -p "{replace with absolute path to the build folder}\libAvKys\Plugins"*
10. run.
