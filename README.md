# FlipsCygwin

*Flips with some pulls merged.*

### Overview

Forked from [Floating IPS](https://github.com/Alcaro/Flips). Changes made thus far:

- Merged [Pull 52](https://github.com/Alcaro/Flips/pull/52) for toggle override checkbox. Making a script for automation isn't worth the hassle when we already have the GUI.
- Merged removal of **Line 14** mentioned in [Issue 32](https://github.com/Alcaro/Flips/issues/32#issuecomment-1036141144) to fix:<br>`multiple definition of '.weak.__cxa_pure_virtual._ZN4fileD2Ev'`
- Added references from [Issue 26](https://github.com/Alcaro/Flips/issues/26#issuecomment-573674247) for context on building with [Cygwin](https://www.cygwin.com/).

# Install Instructions

### Build (Windows, Cygwin)

1. Download and run the [Cygwin](https://www.cygwin.com/) installer.
2. Select these packages:<br>`git`<br>`make`<br>`mingw64-x86_64-gcc-core`<br>`mingw64-x86_64-gcc-g++`<br>`mingw64-x86_64-headers`<br>`mingw64-x86_64-runtime`
3. Download and install all.
4. You should probably restart your system for good measure.
5. Open the **Cygwin Terminal** and enter the following:

```
git clone https://github.com/subvod/FlipsCygwin
mkdir obj
windres flips.rc obj/rc.o
```

7. To build:<br>&emsp;32-bit:<br>&emsp;&emsp;`i686-w64-mingw32-g++ *.c *.cpp obj/rc.o -mwindows -lgdi32 -lcomdlg32 -lcomctl32 -luser32 -lkernel32 -lshell32 -ladvapi32 -fno-exceptions -fno-rtti -o flips.exe`<br>&emsp;64-bit:<br>&emsp;&emsp;`x86_64-w64-mingw32-g++ *.c *.cpp obj/rc.o -mwindows -lgdi32 -lcomdlg32 -lcomctl32 -luser32 -lkernel32 -lshell32 -ladvapi32 -fno-exceptions -fno-rtti -o flips.exe`

### Usage

- Same as the original Flips, but now with a fancy checksum mismatch override toggle checkbox. Also should compile from **Cygwin** with **mingw64** right out of the box after cloning. It does for me.
