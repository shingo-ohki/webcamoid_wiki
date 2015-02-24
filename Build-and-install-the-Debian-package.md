Works also for Ubuntu, Linux Mint and derivatives.

1. Download the latest source of Webcamoid from [here](https://github.com/hipersayanX/webcamoid/releases):

        wget -c -O webcamoid-6.0.0.tar.gz http://github.com/hipersayanX/webcamoid/archive/6.0.0.tar.gz

2. Extract the sources:

        tar -zxvf webcamoid-6.0.0.tar.gz

3. Create the **.oring** file:

        tar -zcvf webcamoid_6.0.0.orig.tar.gz webcamoid-6.0.0/

4. Change the directory to the source directory:

        cd webcamoid-6.0.0

5. Install the package **build-essential**:

        sudo apt-get install build-essential

6. Build the package (if it asks for build dependencies, install it and build again):

        dpkg-buildpackage -us -uc

7. Change to the parent directory:

        cd ..

8. And install the package:

        sudo apt-get install webcamoid_6.0.0-1_amd64.deb

More info [here](https://www.debian.org/doc/manuals/maint-guide/first.en.html#non-native-dh-make) and [here](https://www.debian.org/doc/manuals/maint-guide/build.en.html#completebuild).