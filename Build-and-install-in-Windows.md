**In progress.**

1. Install Qt from [here](http://qt-project.org/downloads).
2. Install MSYS from [here](http://downloads.sourceforge.net/mingw/MSYS-1.0.11.exe).
3. Edit the _C:\MinGW\msys\1.0\etc\fstab_ file and write some shortcuts:

        #Win32_Path                  Mount_Point
        C:\MinGW                     /mingw
        C:\Users\YourUser\Documents  /documents
        C:\Users\YourUser\Desktop    /desktop
        C:\Qt\5.3\mingw482_32\bin    /qttools

4. Open the MSYS console and install the build system:

        mingw-get install mingw-developer-toolkit mingw-base mingw-gcc-g++ msys-base msys-unzip  msys-wget msys-w32api

5. In the MSYS console move to the _Webcamoid/ports/msys_ folder.

        cd /documents/Webcamoid-6.1.0/ports/msys

6. Execute the build script:

        ./build.sh

More info [here](http://mingw.org/wiki/msys) and [here](http://mingw.org/wiki/Getting_Started).
