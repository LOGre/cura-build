# cura-build-i386

This repository contains build scripts used to build Cura and all dependencies from scratch on a Linux i386 machine.
Tested only on an Ubuntu Trusty (14.04) setup.
Experimental : Some dependencies might require manual installing.

## OS X

Use the official Cura build project : https://github.com/Ultimaker/cura-build

## Windows

Use the official Cura build project : https://github.com/Ultimaker/cura-build

## Ubuntu/Linux (Trusty, probably needs tweaking for younger releases).

cura-build can build Ubuntu/Debian packages of Cura.

Dependencies (Needs updating):

* git
* python3 (>= 3.4.0)
* python3-dev (>= 3.4.0)
* python3-pyqt5 (>= 5.4.0)
* python3-pyqt5.qtopengl (>= 5.4.0)
* python3-pyqt5.qtquick (>= 5.4.0)
* python3-pyqt5.qtsvg (>= 5.4.0)
* python3-numpy (>= 1.8.0)
* python3-serial (>= 2.6)
* python3-opengl (>= 3.0)
* python3-setuptools
* libqt5designer5
* libqt5gui5
* libqt5help5
* libqt5printsupport5
* libqt5widgets5
* libqt5opengl5
* libqt5quick5
* libqt5svg5
* libxcb1-dev
* libx11-dev
* build-essential
* pkg-config
* zlib1g
* software-properties-common
* cmake (>= 3.2)
* sip
* gcc (>= 4.9)
* gfortran (>= 4.9)
* python3-pip
* pytest-runner (for use by python 3)
* mesa-utils (only needed at runtime)
* qtbase5-dev (only needed at runtime)

To build, make sure these dependencies are installed, then clone this repository :

```shell
sudo -E add-apt-repository ppa:george-edison55/cmake-3.x
sudo -E add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get install git python3 python3-dev python3-pyqt5 python3-pyqt5.qtopengl python3-pyqt5.qtquick python3-pyqt5.qtsvg python3-numpy python3-serial python3-opengl python3-setuptools libqt5designer5 libqt5gui5 libqt5help5 libqt5printsupport5 libqt5widgets5 libqt5opengl5 libqt5quick5 libqt5svg5 libxcb1-dev libx11-dev build-essential pkg-config zlib1g software-properties-common cmake sip-dev gcc-4.9 g++-4.9 gfortran-4.9 python3-pip mesa-utils qtbase5-dev
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.9 60 --slave /usr/bin/g++ g++ /usr/bin/g++-4.9
sudo update-alternatives --install /usr/bin/gfortran gfortran /usr/bin/gfortran-4.9 60
sudo -E pip3 install pytest-runner
git clone http://github.com/Logre/cura-build-i386.git
```

And then run the following commands from your clone :

```shell
cd cura-build-i386
mkdir build
cd build
cmake ..
make
make package
```

## CentOS/Linux (untested, outdated instructions)

cura-build can build CentOS/RHEL packages of Cura.

Dependencies:

* gcc-gfortran 
* python34.x86_64 
* python34-devel.x86_64 
* python34-numpy.x86_64 
* pyserial.noarch 
* PyOpenGL.noarch 
* python34-setuptools.noarch 
* wxPython.x86_64 
* libstdc++-static.x86_64 
* libstdc++-devel.x86_64 
* openssl.x86_64 
* openblas-devel.x86_64 
* python34-numpy-f2py.x86_64

To build, make sure these dependencies are installed, then clone this repository and run the following commands from your clone:

```shell
sudo yum install gcc-gfortran python34.x86_64 python34-devel.x86_64 python34-numpy.x86_64 pyserial.noarch PyOpenGL.noarch python34-setuptools.noarch wxPython.x86_64 libstdc++-static.x86_64 libstdc++-devel.x86_64 openssl.x86_64 openblas-devel.x86_64 python34-numpy-f2py.x86_64
```
1. download and install scipy from https://github.com/scipy/scipy/releases be sure to use python 3.4, eg. using sudo python3 setup.py 2. install (version in repository is for python 2.7)
3. download and install CMake from https://cmake.org/download/ and configure CMake to use ssl
4. download and install Qt5 from https://www.qt.io/download/
5. download and install PyQt5 from https://www.riverbankcomputing.com/software/pyqt/download5
6. download and install sip from https://www.riverbankcomputing.com/software/sip/download make sure the verion is 4.18 or newer

Alternative method for installing python at: https://edwards.sdsu.edu/research/installing-python3-4-and-the-scipy-stack-on-centos/ .
Make sure, that the PYTHONPATH can find dist-packages. 

```shell
git clone http://github.com/Ultimaker/cura-build.git
cd cura-build
```

```shell
mkdir build
cd build
cmake ..
make
make package
```
