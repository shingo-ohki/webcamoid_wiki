Works for Fedora, OpenSUSE and Mageia.

1. Create the build directories:

        mkdir -p ~/rpmbuild/{SRPMS,SOURCES,SPECS,tmp}

2. Change to the sources directory:

        cd ~/rpmbuild/SOURCES

3. Download the latest source of Webcamoid from [here](https://github.com/hipersayanX/webcamoid/releases):

        wget -c -O webcamoid-6.1.0.tar.gz http://github.com/hipersayanX/webcamoid/archive/6.1.0.tar.gz

4. Extract the sources:

        tar -zxvf webcamoid-6.1.0.tar.gz

5. Change to your home directory:

        cd ~

6. Copy the **.spec** file to your home:

        cp -vf ~/rpmbuild/SOURCES/webcamoid-6.1.0/ports/rpm/webcamoid.spec ~

7. Install the **rpm-build** package:  
    **Fedora**

        sudo yum install rpm-build

    **OpenSUSE**

        sudo zypper install rpm-build

    **Mageia**

        sudo urpmi rpm-build

8. Build the package (if it asks for build dependencies, install it and build again):

        rpmbuild -ba ~/webcamoid.spec

9. Change to the packages directory:

        cd ~/rpmbuild/RPMS/x86_64

10. And install the package:  
    **Fedora**

        sudo rpm -ivh webcamoid-6.1.0-1.fc21.x86_64.rpm

    **OpenSUSE and Mageia**

        sudo rpm -ivh webcamoid-6.1.0-1.x86_64.rpm

More info [here](https://wiki.mageia.org/en/Packagers_RPM_tutorial#Install_required_package).
