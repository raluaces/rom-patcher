# ROM Patcher

[![Build Status](https://build.cssnr.com/buildStatus/icon?job=rom-patcher%20Release%20Builder%20Master)](https://build.cssnr.com/job/rom-patcher%20Release%20Builder%20Master)

This is a Beta product and may contain bugs or lack functionality. Please open issues for any major bugs.

## Download

To download a binary head over to the [Releases Page](https://github.com/smashedr/rom-patcher/releases)

#### Windows

| Package | Details | Filename |
| --- | --- | --- |
| Installer | **Recommended package** | rom-patcher-installer.exe |
| Zipped | Main package archived | rom-patcher.zip |
| Portable | Single executable, slower loading | rom-patcher.exe |

If you get an error about "MSVCP140.dll" missing you may need the latest Visual C++ Libraries:  
https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads  

#### Linux
 
| Package | Details | Filename |
| --- | --- | --- |
| Tarball | Main package archived | rom-patcher.tar.gz |
| Portable | Single executable, slower loading | rom-patcher-onefile.tar.gz |

If you get an error about "flips-linux" not found on a 64-bit OS you may need to install 32-bit glibc++ libs.

## About

This tool allows you to copy download URL's from SMW Central (and some other platforms) and paste it into the source box; and will download the remote resource, unarchive it, and patch it with 1 click of a button.

https://www.smwcentral.net/?p=section&s=smwhacks

![Screen Shot](https://i.imgur.com/zSej6xD.jpg)

## Usage

1. Find a ROM Hack from SMW Central (or anywhere else) and copy the download link. It also may work with the URL from your address bar but is guaranteed to work with the download link. You may also specify an already downloaded patch file or zip containing an patch file. This goes in the first box.

Example: https://dl.smwcentral.net/17289/GPW1.2.zip

2. This is the location to the source ROM from which the patch file will be used with. This file will not be modified, a new output file will be created in the directory specified below.

Example: C:/ROMS/Super Mario World (USA).sfc

3. The output directory where the new patched ROM hack will be generated.

Example: (anywhere you want, maybe the desktop?)

4. Click "Patch ROM". The final rom location will display in the status box then you can click open directory to find it.

## Building

You will need the required `bin` directory with flips for your OS.

#### Windows

Install the requirements.txt plus pyinstaller then build with:
```
powershell.exe .\scripts\build.ps1
```

After building you can create an installer with inno setup by running:
```
ISCC.exe rom-patcher.iss
```

- `bin`: https://jenkins.imgg.site/static/rom-patcher-gui/bin.zip

#### Linux

Install the requirements.txt plus pyinstaller then build with:  
```
bash scripts/build.sh
```

- `bin`: https://jenkins.imgg.site/static/rom-patcher-gui/bin-linux.zip

#### macOS

This app currently does **not** function on macOS due to missing `flips` binary; otherwise will compile just fine.

If anyone wants to write working python code for bps and ips that would be amazing!

## Third Party Software

The following open source software was used in the creation of this tool.

#### Floating IPS

This software uses Floating IPS to patch roms which is bundled with pre-built binaries.

More information and source here: https://www.smwcentral.net/?p=section&a=details&id=11474

#### PyQt5

This software was built using PyQt5 by Riverbank Computing Limited.

More information and source here: https://www.riverbankcomputing.com/software/pyqt/intro

#### Inno Setup

The installer was built using Inno Setup by Jordan Russell’s Software.

More information and source here: http://jrsoftware.org/isinfo.php
