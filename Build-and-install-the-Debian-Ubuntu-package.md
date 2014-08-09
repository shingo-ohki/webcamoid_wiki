1. Download the latest source of Webcamoid from [here](https://github.com/hipersayanX/Webcamoid/releases):  
    wget -c -O Webcamoid-5.0.0.tar.gz http://github.com/hipersayanX/Webcamoid/archive/v5.0.0.tar.gz
2. Extract the sources:  
    tar -zxvf Webcamoid-5.0.0.tar.gz
3. Change the name of the extracted folder:  
    mv -vf Webcamoid-5.0.0 webcamoid-5.0.0
3. Create the **.oring** file:  
    tar -zcvf webcamoid_5.0.0.orig.tar.gz webcamoid-5.0.0/
4. Change the directory to the source directory:  
    cd webcamoid-5.0.0
5. Install the package **build-essential**:  
    sudo apt-get install build-essential
6. Build the package (if this asks for build dependencies, install it and build again):  
    dpkg-buildpackage -us -uc
7. Change to the parent directory:  
    cd ..
8. And install the package:  
    sudo apt-get install webcamoid_5.0.0-1_amd64.deb
