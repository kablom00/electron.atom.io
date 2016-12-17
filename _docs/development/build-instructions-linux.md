---
version: v1.4.12
category: Development
redirect_from:
  - /docs/v0.37.8/development/build-instructions-linux
  - /docs/v0.37.7/development/build-instructions-linux
  - /docs/v0.37.6/development/build-instructions-linux
  - /docs/v0.37.5/development/build-instructions-linux
  - /docs/v0.37.4/development/build-instructions-linux
  - /docs/v0.37.3/development/build-instructions-linux
  - /docs/v0.36.12/development/build-instructions-linux
  - /docs/v0.37.1/development/build-instructions-linux
  - /docs/v0.37.0/development/build-instructions-linux
  - /docs/v0.36.11/development/build-instructions-linux
  - /docs/v0.36.10/development/build-instructions-linux
  - /docs/v0.36.9/development/build-instructions-linux
  - /docs/v0.36.8/development/build-instructions-linux
  - /docs/v0.36.7/development/build-instructions-linux
  - /docs/v0.36.6/development/build-instructions-linux
  - /docs/v0.36.5/development/build-instructions-linux
  - /docs/v0.36.4/development/build-instructions-linux
  - /docs/v0.36.3/development/build-instructions-linux
  - /docs/v0.35.5/development/build-instructions-linux
  - /docs/v0.36.2/development/build-instructions-linux
  - /docs/v0.36.0/development/build-instructions-linux
  - /docs/v0.35.4/development/build-instructions-linux
  - /docs/v0.35.3/development/build-instructions-linux
  - /docs/v0.35.2/development/build-instructions-linux
  - /docs/v0.34.4/development/build-instructions-linux
  - /docs/v0.35.1/development/build-instructions-linux
  - /docs/v0.34.3/development/build-instructions-linux
  - /docs/v0.34.2/development/build-instructions-linux
  - /docs/v0.34.1/development/build-instructions-linux
  - /docs/v0.34.0/development/build-instructions-linux
  - /docs/v0.33.9/development/build-instructions-linux
  - /docs/v0.33.8/development/build-instructions-linux
  - /docs/v0.33.7/development/build-instructions-linux
  - /docs/v0.33.6/development/build-instructions-linux
  - /docs/v0.33.4/development/build-instructions-linux
  - /docs/v0.33.3/development/build-instructions-linux
  - /docs/v0.33.2/development/build-instructions-linux
  - /docs/v0.33.1/development/build-instructions-linux
  - /docs/v0.33.0/development/build-instructions-linux
  - /docs/v0.32.3/development/build-instructions-linux
  - /docs/v0.32.2/development/build-instructions-linux
  - /docs/v0.31.2/development/build-instructions-linux
  - /docs/v0.31.0/development/build-instructions-linux
  - /docs/v0.30.4/development/build-instructions-linux
  - /docs/v0.29.2/development/build-instructions-linux
  - /docs/v0.29.1/development/build-instructions-linux
  - /docs/v0.28.3/development/build-instructions-linux
  - /docs/v0.28.2/development/build-instructions-linux
  - /docs/v0.28.1/development/build-instructions-linux
  - /docs/v0.28.0/development/build-instructions-linux
  - /docs/v0.27.3/development/build-instructions-linux
  - /docs/v0.27.2/development/build-instructions-linux
  - /docs/v0.27.1/development/build-instructions-linux
  - /docs/v0.27.0/development/build-instructions-linux
  - /docs/v0.26.1/development/build-instructions-linux
  - /docs/v0.26.0/development/build-instructions-linux
  - /docs/v0.25.3/development/build-instructions-linux
  - /docs/v0.25.2/development/build-instructions-linux
  - /docs/v0.25.1/development/build-instructions-linux
  - /docs/v0.25.0/development/build-instructions-linux
  - /docs/v0.24.0/development/build-instructions-linux
  - /docs/v0.23.0/development/build-instructions-linux
  - /docs/v0.22.3/development/build-instructions-linux
  - /docs/v0.22.2/development/build-instructions-linux
  - /docs/v0.22.1/development/build-instructions-linux
  - /docs/v0.21.3/development/build-instructions-linux
  - /docs/v0.21.2/development/build-instructions-linux
  - /docs/v0.21.1/development/build-instructions-linux
  - /docs/v0.21.0/development/build-instructions-linux
  - /docs/v0.20.8/development/build-instructions-linux
  - /docs/v0.20.7/development/build-instructions-linux
  - /docs/v0.20.6/development/build-instructions-linux
  - /docs/v0.20.5/development/build-instructions-linux
  - /docs/v0.20.4/development/build-instructions-linux
  - /docs/v0.20.3/development/build-instructions-linux
  - /docs/v0.20.2/development/build-instructions-linux
  - /docs/v0.20.1/development/build-instructions-linux
  - /docs/v0.20.0/development/build-instructions-linux
  - /docs/vlatest/development/build-instructions-linux
source_url: 'https://github.com/electron/electron/blob/master/docs/development/build-instructions-linux.md'
title: Build Instructions (Linux)
excerpt: ''
sort_title: build-instructions-linux
---
# Build Instructions (Linux)

Follow the guidelines below for building Electron on Linux.

## Prerequisites

*   At least 25GB disk space and 8GB RAM.
*   Python 2.7.x. Some distributions like CentOS still use Python 2.6.x so you may need to check your Python version with `python -V`.
*   Node.js. There are various ways to install Node. You can download source code from [Node.js](http://nodejs.org) and compile from source. Doing so permits installing Node on your own home directory as a standard user. Or try repositories such as [NodeSource](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories).
*   Clang 3.4 or later.
*   Development headers of GTK+ and libnotify.

On Ubuntu, install the following libraries:

    $ sudo apt-get install build-essential clang libdbus-1-dev libgtk2.0-dev \
                           libnotify-dev libgnome-keyring-dev libgconf2-dev \
                           libasound2-dev libcap-dev libcups2-dev libxtst-dev \
                           libxss1 libnss3-dev gcc-multilib g++-multilib curl \
                           gperf bison

On Fedora, install the following libraries:

    $ sudo yum install clang dbus-devel gtk2-devel libnotify-devel libgnome-keyring-devel \
                       xorg-x11-server-utils libcap-devel cups-devel libXtst-devel \
                       alsa-lib-devel libXrandr-devel GConf2-devel nss-devel bison \
                       gperf

Other distributions may offer similar packages for installation via package managers such as pacman. Or one can compile from source code.

## Getting the Code

    $ git clone https://github.com/electron/electron.git

## Bootstrapping

The bootstrap script will download all necessary build dependencies and create the build project files. You must have Python 2.7.x for the script to succeed. Downloading certain files can take a long time. Notice that we are using `ninja` to build Electron so there is no `Makefile` generated.

    $ cd electron
    $ ./script/bootstrap.py -v

### Cross compilation

If you want to build for an `arm` target you should also install the following dependencies:

    $ sudo apt-get install libc6-dev-armhf-cross linux-libc-dev-armhf-cross \
                           g++-arm-linux-gnueabihf

And to cross compile for `arm` or `ia32` targets, you should pass the `--target_arch` parameter to the `bootstrap.py` script:

    $ ./script/bootstrap.py -v --target_arch=arm

## Building

If you would like to build both `Release` and `Debug` targets:

    $ ./script/build.py

This script will cause a very large Electron executable to be placed in the directory `out/R`. The file size is in excess of 1.3 gigabytes. This happens because the Release target binary contains debugging symbols. To reduce the file size, run the `create-dist.py` script:

    $ ./script/create-dist.py

This will put a working distribution with much smaller file sizes in the `dist` directory. After running the create-dist.py script, you may want to remove the 1.3+ gigabyte binary which is still in `out/R`.

You can also build the `Debug` target only:

    $ ./script/build.py -c D

After building is done, you can find the `electron` debug binary under `out/D`.

## Cleaning

To clean the build files:

    $ npm run clean

## Troubleshooting

### Error While Loading Shared Libraries: libtinfo.so.5

Prebulit `clang` will try to link to `libtinfo.so.5`. Depending on the host architecture, symlink to appropriate `libncurses`:

    $ sudo ln -s /usr/lib/libncurses.so.5 /usr/lib/libtinfo.so.5

## Tests

See [Build System Overview: Tests](/docs/development/build-system-overview#tests)

## Advanced topics

The default building configuration is targeted for major desktop Linux distributions, to build for a specific distribution or device, following information may help you.

### Building `libchromiumcontent` locally

To avoid using the prebuilt binaries of `libchromiumcontent`, you can pass the `--build_libchromiumcontent` switch to `bootstrap.py` script:

    $ ./script/bootstrap.py -v --build_libchromiumcontent

Note that by default the `shared_library` configuration is not built, so you can only build `Release` version of Electron if you use this mode:

    $ ./script/build.py -c R

### Using system `clang` instead of downloaded `clang` binaries

By default Electron is built with prebuilt `clang` binaries provided by Chromium project. If for some reason you want to build with the `clang` installed in your system, you can call `bootstrap.py` with `--clang_dir=<path>` switch. By passing it the build script will assume the `clang` binaries reside in `<path>/bin/`.

For example if you installed `clang` under `/user/local/bin/clang`:

    $ ./script/bootstrap.py -v --build_libchromiumcontent --clang_dir /usr/local
    $ ./script/build.py -c R

### Using other compilers other than `clang`

To build Electron with compilers like `g++`, you first need to disable `clang` with `--disable_clang` switch first, and then set `CC` and `CXX` environment variables to the ones you want.

For example building with GCC toolchain:

    $ env CC=gcc CXX=g++ ./script/bootstrap.py -v --build_libchromiumcontent --disable_clang
    $ ./script/build.py -c R

### Environment variables

Apart from `CC` and `CXX`, you can also set following environment variables to custom the building configurations:

*   `CPPFLAGS`
*   `CPPFLAGS_host`
*   `CFLAGS`
*   `CFLAGS_host`
*   `CXXFLAGS`
*   `CXXFLAGS_host`
*   `AR`
*   `AR_host`
*   `CC`
*   `CC_host`
*   `CXX`
*   `CXX_host`
*   `LDFLAGS`

The environment variables have to be set when executing the `bootstrap.py` script, it won't work in the `build.py` script.
