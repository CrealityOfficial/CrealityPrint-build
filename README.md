CrealityPrint-build
=======

CrealityPrint is FDM-slicer desktop software of [Creality 创想三维](https://www.creality.cn/).

this is a description project base on **repo** 

![20230831-122813](C:\Users\cx1959\Desktop\20230831-122813.jpg)

## description

- **model (edit,  model library)**
- **slice**
- **net**

relates
-------------

- [Python 3.9](https://www.python.org/)
- [CMake 3.23 or higher](https://cmake.org/)
- [Conan >=1.50 <=1.56.0](https://conan.io/)
- [repo](https://source.android.com/docs/setup/create/repo?hl=zh-cn)
- compile toolchains  
- [conan_build](https://github.com/CrealityOfficial/conan_build) 

## build 

1. build conan_build to prepare the pre-compiled libraries

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