You can download the binary packages for Arch, Debian, Fedora, openSUSE, and Ubuntu from [openSUSE Build Service](https://build.opensuse.org/package/show/home:hipersayan_x/Webcamoid). However, packages in OBS are just for testing purpose and doesn't receive the status of official. It's highly recommended to install Webcamoid from the official repositories of your distro, if it's not available in your distro, ask your distro maintainers to consider including Webcamoid in their repositories.

# Arch #

**Webcamoid is officially supported in the [AUR](https://aur.archlinux.org/packages/webcamoid) [repositories](https://aur.archlinux.org/packages/webcamoid-git) and it's the preferred install method**. There is also possible to install the Webcamoid binary package from OBS.
Edit your */etc/pacman.conf* and add the following lines to the end of the file:

    [home_hipersayan_x_Arch_Extra]
    SigLevel = Never
    Server = http://download.opensuse.org/repositories/home:/hipersayan_x/Arch_Extra/$arch

Then update your repositories

    sudo pacman -Syy

And install Webcamoid as:

    sudo pacman -S webcamoid-gstreamer

# Debian #

Webcamoid is available in the **main** [repository](https://packages.debian.org/sid/webcamoid) of Debian, for **Stretch** and higher. Install Webcamoid as:

    sudo apt-get install webcamoid

# Fedora #

Fedora is supported since **Fedora 23** from OBS. First add the repository:

    yum-config-manager --add-repo http://download.opensuse.org/repositories/home:/hipersayan_x/Fedora_23/home:hipersayan_x.repo

Then install Webcamoid as:

    yum install webcamoid akqml avkys-plugins

# openSUSE #

Webcamoid is supported since **Leap**, **Factory** and **Tumbleweed**. First add the repository:

## Leap ##

    zypper ar -f http://download.opensuse.org/repositories/home:/hipersayan_x/openSUSE_Leap_42.1/ webcamoid


## Factory ##

    zypper ar -f http://download.opensuse.org/repositories/home:/hipersayan_x/openSUSE_Factory/ webcamoid


## Tumbleweed ##

    zypper ar -f http://download.opensuse.org/repositories/home:/hipersayan_x/openSUSE_Tumbleweed/ webcamoid

Then install Webcamoid as:

    zypper install webcamoid akqml avkys-plugins

# Ubuntu #

Webcamoid is available in the **universe** [repository](http://packages.ubuntu.com/xenial/webcamoid) of Ubuntu, for branches **xenial** (16.04) and higher. Install Webcamoid as:

    sudo apt-get install webcamoid
