---
version: v1.4.12
category: Development
redirect_from:
  - /docs/v0.37.8/development/build-instructions-windows
  - /docs/v0.37.7/development/build-instructions-windows
  - /docs/v0.37.6/development/build-instructions-windows
  - /docs/v0.37.5/development/build-instructions-windows
  - /docs/v0.37.4/development/build-instructions-windows
  - /docs/v0.37.3/development/build-instructions-windows
  - /docs/v0.36.12/development/build-instructions-windows
  - /docs/v0.37.1/development/build-instructions-windows
  - /docs/v0.37.0/development/build-instructions-windows
  - /docs/v0.36.11/development/build-instructions-windows
  - /docs/v0.36.10/development/build-instructions-windows
  - /docs/v0.36.9/development/build-instructions-windows
  - /docs/v0.36.8/development/build-instructions-windows
  - /docs/v0.36.7/development/build-instructions-windows
  - /docs/v0.36.6/development/build-instructions-windows
  - /docs/v0.36.5/development/build-instructions-windows
  - /docs/v0.36.4/development/build-instructions-windows
  - /docs/v0.36.3/development/build-instructions-windows
  - /docs/v0.35.5/development/build-instructions-windows
  - /docs/v0.36.2/development/build-instructions-windows
  - /docs/v0.36.0/development/build-instructions-windows
  - /docs/v0.35.4/development/build-instructions-windows
  - /docs/v0.35.3/development/build-instructions-windows
  - /docs/v0.35.2/development/build-instructions-windows
  - /docs/v0.34.4/development/build-instructions-windows
  - /docs/v0.35.1/development/build-instructions-windows
  - /docs/v0.34.3/development/build-instructions-windows
  - /docs/v0.34.2/development/build-instructions-windows
  - /docs/v0.34.1/development/build-instructions-windows
  - /docs/v0.34.0/development/build-instructions-windows
  - /docs/v0.33.9/development/build-instructions-windows
  - /docs/v0.33.8/development/build-instructions-windows
  - /docs/v0.33.7/development/build-instructions-windows
  - /docs/v0.33.6/development/build-instructions-windows
  - /docs/v0.33.4/development/build-instructions-windows
  - /docs/v0.33.3/development/build-instructions-windows
  - /docs/v0.33.2/development/build-instructions-windows
  - /docs/v0.33.1/development/build-instructions-windows
  - /docs/v0.33.0/development/build-instructions-windows
  - /docs/v0.32.3/development/build-instructions-windows
  - /docs/v0.32.2/development/build-instructions-windows
  - /docs/v0.31.2/development/build-instructions-windows
  - /docs/v0.31.0/development/build-instructions-windows
  - /docs/v0.30.4/development/build-instructions-windows
  - /docs/v0.29.2/development/build-instructions-windows
  - /docs/v0.29.1/development/build-instructions-windows
  - /docs/v0.28.3/development/build-instructions-windows
  - /docs/v0.28.2/development/build-instructions-windows
  - /docs/v0.28.1/development/build-instructions-windows
  - /docs/v0.28.0/development/build-instructions-windows
  - /docs/v0.27.3/development/build-instructions-windows
  - /docs/v0.27.2/development/build-instructions-windows
  - /docs/v0.27.1/development/build-instructions-windows
  - /docs/v0.27.0/development/build-instructions-windows
  - /docs/v0.26.1/development/build-instructions-windows
  - /docs/v0.26.0/development/build-instructions-windows
  - /docs/v0.25.3/development/build-instructions-windows
  - /docs/v0.25.2/development/build-instructions-windows
  - /docs/v0.25.1/development/build-instructions-windows
  - /docs/v0.25.0/development/build-instructions-windows
  - /docs/v0.24.0/development/build-instructions-windows
  - /docs/v0.23.0/development/build-instructions-windows
  - /docs/v0.22.3/development/build-instructions-windows
  - /docs/v0.22.2/development/build-instructions-windows
  - /docs/v0.22.1/development/build-instructions-windows
  - /docs/v0.21.3/development/build-instructions-windows
  - /docs/v0.21.2/development/build-instructions-windows
  - /docs/v0.21.1/development/build-instructions-windows
  - /docs/v0.21.0/development/build-instructions-windows
  - /docs/v0.20.8/development/build-instructions-windows
  - /docs/v0.20.7/development/build-instructions-windows
  - /docs/v0.20.6/development/build-instructions-windows
  - /docs/v0.20.5/development/build-instructions-windows
  - /docs/v0.20.4/development/build-instructions-windows
  - /docs/v0.20.3/development/build-instructions-windows
  - /docs/v0.20.2/development/build-instructions-windows
  - /docs/v0.20.1/development/build-instructions-windows
  - /docs/v0.20.0/development/build-instructions-windows
  - /docs/vlatest/development/build-instructions-windows
source_url: 'https://github.com/electron/electron/blob/master/docs/development/build-instructions-windows.md'
title: Build Instructions (Windows)
excerpt: ''
sort_title: build-instructions-windows
---
# Build Instructions (Windows)

Follow the guidelines below for building Electron on Windows.

## Prerequisites

*   Windows 7 / Server 2008 R2 or higher
*   Visual Studio 2015 - [download VS 2015 Community Edition for free](https://www.visualstudio.com/en-us/products/visual-studio-community-vs.aspx)
*   [Python 2.7](http://www.python.org/download/releases/2.7/)
*   [Node.js](http://nodejs.org/download/)
*   [Git](http://git-scm.com)

If you don't currently have a Windows installation, [dev.microsoftedge.com](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/) has timebombed versions of Windows that you can use to build Electron.

Building Electron is done entirely with command-line scripts and cannot be done with Visual Studio. You can develop Electron with any editor but support for building with Visual Studio will come in the future.

**Note:** Even though Visual Studio is not used for building, it's still **required** because we need the build toolchains it provides.

**Note:** While older versions of Electron required Visual Studio 2013, Electron 1.1 and later does require Visual Studio 2015.

## Getting the Code

    $ git clone https://github.com/electron/electron.git

## Bootstrapping

The bootstrap script will download all necessary build dependencies and create the build project files. Notice that we're using `ninja` to build Electron so there is no Visual Studio project generated.

    $ cd electron
    $ python script\bootstrap.py -v

## Building

Build both Release and Debug targets:

    $ python script\build.py

You can also only build the Debug target:

    $ python script\build.py -c D

After building is done, you can find `electron.exe` under `out\D` (debug target) or under `out\R` (release target).

## 32bit Build

To build for the 32bit target, you need to pass `--target_arch=ia32` when running the bootstrap script:

    $ python script\bootstrap.py -v --target_arch=ia32

The other building steps are exactly the same.

## Visual Studio project

To generate a Visual Studio project, you can pass the `--msvs` parameter:

    $ python script\bootstrap.py --msvs

## Cleaning

To clean the build files:

    $ npm run clean

## Tests

See [Build System Overview: Tests](/docs/development/build-system-overview#tests)

## Troubleshooting

### Command xxxx not found

If you encountered an error like `Command xxxx not found`, you may try to use the `VS2015 Command Prompt` console to execute the build scripts.

### Fatal internal compiler error: C1001

Make sure you have the latest Visual Studio update installed.

### Assertion failed: ((handle))->activecnt >= 0

If building under Cygwin, you may see `bootstrap.py` failed with following error:

    Assertion failed: ((handle))->activecnt >= 0, file src\win\pipe.c, line 1430

    Traceback (most recent call last):
      File "script/bootstrap.py", line 87, in <module>
        sys.exit(main())
      File "script/bootstrap.py", line 22, in main
        update_node_modules('.')
      File "script/bootstrap.py", line 56, in update_node_modules
        execute([NPM, 'install'])
      File "/home/zcbenz/codes/raven/script/lib/util.py", line 118, in execute
        raise e
    subprocess.CalledProcessError: Command '['npm.cmd', 'install']' returned non-zero exit status 3

This is caused by a bug when using Cygwin Python and Win32 Node together. The solution is to use the Win32 Python to execute the bootstrap script (assuming you have installed Python under `C:\Python27`):

    $ /cygdrive/c/Python27/python.exe script/bootstrap.py

### LNK1181: cannot open input file 'kernel32.lib'

Try reinstalling 32bit Node.js.

### Error: ENOENT, stat 'C:\Users\USERNAME\AppData\Roaming\npm'

Simply making that directory [should fix the problem](http://stackoverflow.com/a/25095327/102704):

    $ mkdir ~\AppData\Roaming\npm

### node-gyp is not recognized as an internal or external command

You may get this error if you are using Git Bash for building, you should use PowerShell or VS2015 Command Prompt instead.
