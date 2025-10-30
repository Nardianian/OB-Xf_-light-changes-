# About this fork
This fork contains only a few changes to the "cmakelists.txt" file to add support for ASIO and Jack2 (Jack4Win) drivers on Windows, and for the VST3, VST2 (sdk 2.4), LV2, and AAX plugin formats, in addition to the standalone version. Please note that VST2 needs Steinberg license and the AAX plugin cannot be used unless it is first activated/authorized following a specific procedure established by Avid, which requires - among other things - Avid and PACE/iLok accounts and the use of tools such as AAX Validator, Pro Tools Developer Bundle, PACE Eden Signing Tools, etc. Additionally, the difficulty in getting the build due to issues with git-versioning necessitated further changes to the cmakelists.txt and the creation of the BUILD_VERSION file in the main directory of the repo.

# Original Readme

# About

OB-Xf is a continuation of the last open source version of OB-Xd by [2DaT](https://github.com/2DaT/Obxd) and later
[discoDSP](https://github.com/reales/OB-Xd), bringing together several efforts going on in the audio space and
combining them inside the Surge Synth Team infrastructure.

The synth is currently in a beta phase, with a few features still under development, but the plugin is feature stable and working rather well, we believe.

# Installing the Synth

We provide installers (signed DMG for macOS, EXE for Windows x64/ARM64/ARM64EC, DEB for Linux x86_64 built on Ubuntu 20) [here](https://github.com/surge-synthesizer/OB-Xf/releases/tag/Nightly). See that page for installation instructions.

# Compatibility with OB-Xd

Patches and banks created by OB-Xd are **NOT (!)** compatible with OB-Xf, due to a number of changes we decided to do for certain parameters.
Patch conversion is likely possible for the most part, but is not the immediate priority, and 100% fidelity to OB-Xd cannot be guaranteed.

# Building

Using CMake:

```bash
git submodule update --init --recursive
cmake -B Builds/Release .
cmake --build Builds/Release --config Release --target obxf-staged
```

This will build supported plugin formats and place them in builds/Release/obxf_products. If you self-build, you are responsible for installing the assets from assets/installer in the appropriate location. When running the plugin or standalone, you will see where OB-Xf attempted to look for assets, if you get it wrong.

# Copyright

This repository and the source code is under GPL3 license. OB-Xf is and always will be free in all contexts and for all uses, with the source code available and modifiable, and the software usable in any context, free or commercial.
