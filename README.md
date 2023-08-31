CrealityPrint-build
=======

CrealityPrint-build is **repo** description project of [CrealityPrint](https://github.com/CrealityOfficial/CrealityPrint) which is the FDM desktop FDM-slicer software of [Creality 创想三维](https://www.creality.cn/).

## description

- **how to build CrealityPrint on Windows**
- **how to build CrealityPrint on MacOS**
- **how to build CrealityPrint on Linux**

relates
-------------

- [Python 3.9](https://www.python.org/)
- [CMake 3.23 or higher](https://cmake.org/)
- [Conan >=1.50 <=1.56.0](https://conan.io/)
- [repo](https://source.android.com/docs/setup/create/repo?hl=zh-cn)
- compile toolchains  (Visual Studio with MSVC 2019 or higher / xcode 13 or higher / gcc8 or higher)
- [conan_build](https://github.com/CrealityOfficial/conan_build) 

## build 

1. use [conan_build](https://github.com/CrealityOfficial/conan_build) to build the dependent  libraries

2. build this base on repo

   Windows

   ```Shell
   repo init -u https://github.com/CrealityOfficial/CrealityPrint-build.git -m release-v4.3.7.xml 
   repo sync
   cd CrealityPrint
   python3 cmake\ci\conan-cmake.py -t opensource-win
   cd win32-build\build
   ninja
   ```

   Mac

   ```Shell
   repo init -u https://github.com/CrealityOfficial/CrealityPrint-build.git -m release-v4.3.7.xml 
   repo sync
   cd CrealityPrint
   python3 cmake/ci/conan-cmake.py -t opensource-mac
   cd mac-build/build
   make -j8
   ```

   Linux

   ```Shell
   repo init -u https://github.com/CrealityOfficial/CrealityPrint-build.git -m release-v4.3.7.xml 
   repo sync
   cd CrealityPrint
   python3 cmake/ci/conan-cmake.py -t opensource-linux
   cd linux-build/build
   ninja
   ```

license
-------

CrealityPrint as a whole is licensed under the GNU General Public License, Version 3.
