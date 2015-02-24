Works for Fedora, OpenSUSE and Mageia.

1. Create the build directories:

        mkdir -p ~/rpmbuild/{SRPMS,SOURCES,SPECS,tmp}

2. Change to the sources directory:

        cd ~/rpmbuild/SOURCES

3. Download the latest source of Webcamoid from [here](https://github.com/hipersayanX/Webcamoid/releases):

        wget -c -O Webcamoid-6.0.0.tar.gz http://github.com/hipersayanX/Webcamoid/archive/6.0.0.tar.gz

4. Extract the sources:

        tar -zxvf Webcamoid-6.0.0.tar.gz

5. Change the name of the extracted folder:

        mv -vf Webcamoid-6.0.0 webcamoid-6.0.0

6. Create the new source file:

        tar -zcvf webcamoid-6.0.0.tar.gz webcamoid-6.0.0/

7. Change to your home directory:

        cd ~

8. Copy the **.spec** file to your home:

        cp -vf ~/rpmbuild/SOURCES/webcamoid-6.0.0/ports/rpm/webcamoid.spec ~

9. Install the **rpm-build** package:  
    **Fedora**

        sudo yum install rpm-build

    **OpenSUSE**

        sudo zypper install rpm-build

    **Mageia**

        sudo urpmi rpm-build

10. Build the package (if it asks for build dependencies, install it and build again):

        rpmbuild -ba ~/webcamoid.spec

11. Change to the packages directory:

        cd ~/rpmbuild/RPMS/x86_64

12. And install the package:  
    **Fedora**

        sudo rpm -ivh webcamoid-6.0.0-1.fc21.x86_64.rpm

    **OpenSUSE and Mageia**

        sudo rpm -ivh webcamoid-6.0.0-1.x86_64.rpm

More info [here](https://wiki.mageia.org/en/Packagers_RPM_tutorial#Install_required_package).
