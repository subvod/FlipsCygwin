# FlipsCygwin

*Flips with some pulls merged.*

### Overview

Forked from [Floating IPS](https://github.com/Alcaro/Flips). I wanted to combine these changes because I'm too lazy to use cmdline. Changes made thus far:

- Merged [Pull 52](https://github.com/Alcaro/Flips/pull/52) for toggle override checkbox. Making a script for automation isn't worth the hassle when we already have the GUI.
- Merged removal of **Line 14** mentioned in [Issue 32](https://github.com/Alcaro/Flips/issues/32#issuecomment-1036141144) to fix:<br>`multiple definition of '.weak.__cxa_pure_virtual._ZN4fileD2Ev'`
- Added references from [Issue 26](https://github.com/Alcaro/Flips/issues/26#issuecomment-573674247) for context on building with [Cygwin](https://www.cygwin.com/).

### Patch Size Comparison

Below are some size comparisons of patches included in [dearman4's Emerald Final](https://www.pokecommunity.com/showthread.php?t=410480). ROM patch data can vary greatly depending on what was changed, so after a decade of not looking into the specifics of this I've forced myself to do so.

`--bps-delta` is best suited for large ASM patches and pretty much any involving GFX:

**Deluxe Gen4 Sprite Patch**

```
FILE: Deluxe Gen4 Sprite patch.ups
SIZE: 16710687 (15.9 MB)
CRC32: 2144DF1C
MD5: 2444ee113995909c21fd07bd68e0bfb5
SHA1: 1ae96a7e1bc75979f77f1873829100e22f86ff76
SHA256: fd3235a86d6fb2f6de05b1307509c80c99d6651548b7376fc08dfc563666dd35
SHA512: 1339e817ae091e897ba8cc6e87b850000dd2fd684f02e0c29ab207a39b0888cb7ba731f4816ef2d79fa1e15370ba3187d498f632e9ee53bd61f28aa103b87f21
SHA3-256: 34e7b067b3002804b5604042ec35d3374e736bfc21e912bd879ab45ba517c648
SHA3-512: 4d064ccc90b95d654b95b13ec880fc5109858275fe0abce7b947e1d5504154f9e21e48181260902514346927ad256ab1612e2fe27150ea9875ea03cfd6056760

FILE: Deluxe Gen4 Sprite Patch.bps
SIZE: 1072187 (1.0 MB)
CRC32: 2144DF1C
MD5: 6241f4ad23b79fdb02e7b62e634aeb3e
SHA1: d0cf2349d19085b301f1219645b4e0b367165d3b
SHA256: 69afc1a20d56e39cb44f75af3194784a0129658b0d9d4f45bb9cd1278decff49
SHA512: f7c3fe2f1950b32a98b0769a1097d4380877ae2a5477c2eca3949def3c36abbc93e02bdfe2044b985a34a40ff984de2c5f634fcb03ce31e7beb1de00f3b687dc
SHA3-256: 3f4d61b0bd40a9783413e013d2eb34c933174aea9cb55e885a2f746710751b6d
SHA3-512: af86c8310ae1e8d9402bca35449b258a3a2a05604787784dd6c25d83ccc6601b814f112a9a4b48a5aec00a4bf7fb404b43fe9906139bf5c71bf23c06816b3954
```

**Deluxe No Gen VI Exp Share**

```
FILE: Deluxe No Gen VI Exp Share.ips
SIZE: 735375 (718.1 KB)
CRC32: 71B529C7
MD5: 64b352538402e51f0d59d953359602a9
SHA1: 1662c9da4fb5a544854e36784d0ac5da9ee3a415
SHA256: 54522b1671c62cfbf5765887ee0d4d75c8d43034c1477ed3b96af27731fd8d29
SHA512: 3f72f13a21bfeba7699ce0126cd49c0ad0e4b7e58f9573f9ab45143dabed93cd7a4734564ff5b4311125bc2f41680850ba162fa51d00cba93e82133ab1b3f255
SHA3-256: bd1135f97bf5affac507339695936495472d5f955abf6528a8cf61050dab53c2
SHA3-512: fb4299902d82ad101f92efeba66723b6a23923f5c2cd1ba12e3af3174cb20d1f92214f2a390c6b91fd5e43a75d8ccb2e54ca9a9345d900acde23595a1e62b76a

FILE: Deluxe No Gen VI Exp Share.bps
SIZE: 418905 (409.1 KB)
CRC32: 2144DF1C
MD5: 0a31a14410c1c69c4eecd74db5812841
SHA1: 3874911b22fee69a1c05fc6443b131b9f727f6cc
SHA256: 377e4c74f2036696b1187b43e8513782aedc0924ab532225a466e5589d5ad64b
SHA512: cc9967f56133f8539cc86905168dc309ddf64e4df3be5fda6910d3941b9ccb5117b69e0d288bcee6c9be9bdc0a420cf884e8602a5e1691301818e7bccd3d5ee6
SHA3-256: 19b9d9a3d8f5a630a2f680842b170b1652451f6c404e6ad1d7ef3621b5ccf6c1
SHA3-512: e24536f0874ad3df7896b3c1c217ab3ea9481be64c209ce4f2a35d9aa785c65d08bc1a9557dc4457f4738cb63f0538b44d7bd791dc96deb60dab06b720883847
```

But, as you can see, `--bps-delta` isn't always the best in terms of final patch size. Small ASM patches are better suited for distribution in `IPS` format:

**Emerald 32-bit TIMER RNG Fix**

```
FILE: Emerald 32-bit TIMER RNG Fix.ips
SIZE: 118 (118.0 bytes)
CRC32: E25F60B5
MD5: 9b5301420a246635dba029e97a7cf2fa
SHA1: 4bc91f692640228346136dbbb4f44222a4475601
SHA256: 713575afc4a485ca9430b7ef46806b7261a74668e958aaf2ee05ea0aa88dc328
SHA512: bf4cd9becbddb73d6982748f2cb618e03d743412d01cc1c48a1e0eb0b234c6e45ddb90b46c4d602e0104e5b50ebc5458738c79f4a865935413f73a6525d2b112
SHA3-256: 2faf7f2d0d098f0afd6aab8cb046af6c9c5b2af7ccc124a52018d6ae5a51e5c1
SHA3-512: e332a3955ff7374a89ddebe8d3a2f9daa12a6afa2282e6cc7e09cf04c122b705b479bc68427218230642cc2df688f82ce8edc988d835caea02e6435cab71e05e

FILE: Emerald 32-bit TIMER RNG Fix.bps
SIZE: 140 (140.0 bytes)
CRC32: 2144DF1C
MD5: cdacecb6197302c5efea62eb9fa9b990
SHA1: a2996e74bf18083adc84938496910f00cad8a7cc
SHA256: c7d3de07854862218f2441cfbe1aa81cf16fd599be0f23526c5800b0e84c6683
SHA512: f33b87d0da88758fa8ad6dbe406bf6ad461a6380dc33314f91f051ee7290442962167ce187d826c8788d6a250506a72df11479dfbbec78845b22b62e922c3d25
SHA3-256: 952c893b678ca807ddc0dfc9e616b47e645348f9b7b9b1acccabe178b3caf0d2
SHA3-512: b82fda0ca6a69e8bfdb19ba48fbdd7adaea3432cd0d8a01ec4455ebb5229d62b031848a170d5f22837eec3cfe03cfc61da30a2f996ff80892fc885fcfba9f691
```

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
6. Open the **Cygwin Terminal** and enter the following to build 64-bit:
```
git clone https://github.com/subvod/FlipsCygwin
windres.exe -J rc -O coff -i *.rc -o resources.o
x86_64-w64-mingw32-g++ -Wall -m64 -O2 -m64 -fno-exceptions -fno-rtti -c *.cpp *.c
x86_64-w64-mingw32-g++ -o flips.exe *.o -m64 -s -m64 -lgdi32 -luser32 -lkernel32 -lcomctl32 -mwindows
rm *.o
```

&emsp;**NOTE:** To build for 32-bit, replace `x86_64-w64-mingw32-g++` with `i686-w64-mingw32-g++`

### Usage

- Same as the original Flips, but now with a fancy checksum mismatch override toggle checkbox. Also should compile from **Cygwin** with **mingw64** right out of the box after cloning. It does for me.
