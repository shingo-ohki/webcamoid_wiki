Works also for Ubuntu, Linux Mint and derivatives.

1. Download the latest source of Webcamoid from [here](https://github.com/webcamoid/webcamoid/releases):

        wget -c -O webcamoid-8.0.0.tar.gz http://github.com/webcamoid/webcamoid/archive/8.0.0.tar.gz

2. Extract the sources:

        tar -zxvf webcamoid-8.0.0.tar.gz

3. Create the **.oring** file:

        tar -zcvf webcamoid_8.0.0.orig.tar.gz webcamoid-8.0.0/

4. Change the directory to the source directory:

        cd webcamoid-8.0.0

5. Move the Debian package folder to the source directory:

        mv -vf ports/debian .

6. Install the package **build-essential**:

        sudo apt-get install build-essential

7. Build the package (if it asks for build dependencies, install it and build again):

        dpkg-buildpackage -us -uc

8. Change to the parent directory:

        cd ..

9. And install the package:

        sudo apt-get install webcamoid_8.0.0-1_amd64.deb

More info [here](https://www.debian.org/doc/manuals/maint-guide/first.en.html#non-native-dh-make) and [here](https://www.debian.org/doc/manuals/maint-guide/build.en.html#completebuild).
