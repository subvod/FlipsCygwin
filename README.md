# FlipsCygwin

*Flips with some pulls merged.*

### Overview

Forked from [Floating IPS](https://github.com/Alcaro/Flips). Changes made thus far:

- Merged [Pull 52](https://github.com/Alcaro/Flips/pull/52) for toggle override checkbox. Making a script for automation isn't worth the hassle when we already have the GUI.
- Merged removal of **Line 14** mentioned in [Issue 32](https://github.com/Alcaro/Flips/issues/32#issuecomment-1036141144) to fix:<br>`multiple definition of '.weak.__cxa_pure_virtual._ZN4fileD2Ev'`
- Added references from [Issue 26](https://github.com/Alcaro/Flips/issues/26#issuecomment-573674247) for context on building with [Cygwin](https://www.cygwin.com/).

# Install Instructions

### Windows (CodeBlocks)

*No, I don't use VS Code. You're on your own with that.*

1. Download and install a binary release of [CodeBlocks](http://www.codeblocks.org/downloads/binaries/#imagesoswindows48pnglogo-microsoft-windows), usually you'll want the one that comes with MinGW unless you know what you're doing. How to set up directories elsewhere, and what not. If that's the case, you ought to know what a nightly is, as well.
2. Download the [release version of this fork](https://github.com/subvod/FlipsCygwin/releases).
3. Start up CodeBlocks and click `File < New < Project...`
4. Select `Win32 GUI Project` and click `Go`
5. Choose `Frame Based`
6. Name the project whatever. Let's say `flips` for now.
7. Choose a folder you'll remember.
8. Compiler should have already been auto-detected, so just click `Finish`
9. Right click `main.cpp` then `Remove file from project`
10. Navigate to the project's folder and delete `main.cpp`
11. Open this fork's release archive and unzip all files in the `src` folder into your project's folder.
12. Back in CodeBlocks, right click your project's name then `Add files...`
13. Select all files in the directory and click `Open`
14. Click `Project < Build options...`
15. At the bottom of the `General` section, tick the checkmark of whatever architecture you want (32 or 64 bit)
16. Click the `Other compiler options` tab and paste: `-fno-exceptions -fno-rtti`
17. Press `F9`

### Windows (Cygwin)

1. Download and run the [Cygwin](https://www.cygwin.com/) installer.
2. Let's assume you want to build for 64-bit. Select these packages:
```
git
make
mingw64-x86_64-gcc-core
mingw64-x86_64-gcc-g++
mingw64-x86_64-headers
mingw64-x86_64-runtime
```
4. Download and install all.
5. You should probably restart your system for good measure.
6. Open the **Cygwin Terminal** and enter the following:
```
git clone https://github.com/subvod/FlipsCygwin
mkdir obj
windres flips.rc obj/rc.o
```
7. To build:<br>&emsp;32-bit:<br>&emsp;&emsp;`i686-w64-mingw32-g++ *.c *.cpp obj/rc.o -mwindows -lgdi32 -lcomdlg32 -lcomctl32 -luser32 -lkernel32 -lshell32 -ladvapi32 -fno-exceptions -fno-rtti -o flips.exe`<br>&emsp;64-bit:<br>&emsp;&emsp;`x86_64-w64-mingw32-g++ *.c *.cpp obj/rc.o -mwindows -lgdi32 -lcomdlg32 -lcomctl32 -luser32 -lkernel32 -lshell32 -ladvapi32 -fno-exceptions -fno-rtti -o flips.exe`

### Usage

- Same as the original Flips, but now with a fancy checksum mismatch override toggle checkbox. Also should compile from **Cygwin** with **mingw64** right out of the box after cloning. It does for me.
