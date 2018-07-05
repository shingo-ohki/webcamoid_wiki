Please, read the [raw build guide](https://github.com/webcamoid/webcamoid/wiki/Raw-build-and-install) and [deploy guide](https://github.com/webcamoid/webcamoid/wiki/Deploy-and-create-self-contained-binary-packages) before reading this guide, there you will find all available configurations to tweak the build.  

Installing dependencies
=======================

Dependencies for software development in GNU/Linux can be really hard to manage and keep updated, specially because there is no a standard way of installing a package. So to keep in sync with project development, this guide will just provide you a link to where you can find the dependencies required to build Webcamoid:

- **Arch**: [check this](https://aur.archlinux.org/packages/webcamoid-git)  
- **Debian**: [check this](https://github.com/webcamoid/webcamoid/blob/master/ports/ci/travis/install_deps.sh#L74)  
- **Fedora**: [check this](https://github.com/webcamoid/webcamoid/blob/master/ports/ci/travis/install_deps.sh#L137)  
- **OpenSUSE**: [check this](https://github.com/webcamoid/webcamoid/blob/master/ports/ci/travis/install_deps.sh#L162)  

Build from Qt Creator
=====================

1. Open *Webcamoid.pro* file with Qt creator.
2. Go to **Projects** tab.
3. This step is optional but may be useful.  
    3.a) You can enable **Shadow build** to put all compiled and generated files in a different folder and leave source directory clean. In the **Build directory** write for example _C:\[path]\webcamoid-shadow_ to put compiled files there.  
    3.a) In **Additional arguments** you can add **CONFIG+=silent** to reduce compile verbosity, and make compile errors easier to notice.
    3.b) In **Build Steps > Make > Make argumments** add **-j[number of supported CPU threads]** to speed up build, for example **-j4**.  
4. This step is also optional but let you create the installer and portable packages. Enabling deploy scripts may slow down the build a lot, so you are advised to disable this if you are just debugging.  
    4.a) In **Build Steps > Add Build Step > Custom Process Step**, in **Command** write **python3**.  
    4.b) In **Argumments** add _/[path]/webcamoid/ports/deploy/deploy.py_.  
    4.c) You can disable this step checking the 🛇 icon near to **Details**.  
5. In **Build & Run > Run > Command line argumments** add:
  
```
-r -p /[path]/webcamoid/libAvKys/Plugins -q /[path]/webcamoid/libAvKys
```
   
   **Note**: If you enabled **Shadow build** replace _/[path]/webcamoid_ with the shadow build folder.  
  
6. Build and run the project.
