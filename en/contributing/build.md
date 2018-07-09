# Building SDK from Source

This section explains how to [build](#build_sdk_cpp) and [install](#install-artifacts) the *Dronecode SDK* C++ library from source (both "natively" and in docker) for all our target platforms. 
It also shows how to build the SDK with extensions and build the API Reference documentation. 


## Build the C++ Library {#build_sdk_cpp}

This section explains how to build the SDK C++ library from source, 
along with its unit and integration tests. 
Build artifacts are created in the **build** subdirectory.

### macOS {#mac-os-x}

First install:
* [XCode](https://developer.apple.com/xcode/) (for *clang*)
* [Homebrew](https://brew.sh/) (for *cmake*).
  Once you have installed brew, you can install *cmake* via the terminal:
  ```
  brew install cmake
  ```

Then follow the instructions for building the library on [Linux](#linux).

### Linux

To build the *Dronecode SDK* C++ Library on Linux (or macOS after installing the [preconditions above](#mac-os-x)):

1. First install the dependencies
   ```bash
   sudo apt-get update -y
   sudo apt-get install cmake build-essential colordiff astyle git libcurl4-openssl-dev libtinyxml2-dev doxygen -y
   ```
   > **Note** If the build reports a missing dependency, confirm that the set above matches the requirements in the [appropriate docker file for your platform](https://github.com/Dronecode/DronecodeSDK/tree/{{ book.github_branch }}/docker).

1. Clone the [DronecodeSDK repository](https://github.com/Dronecode/DronecodeSDK) (or your fork): 
   ```sh
   git clone https://github.com/Dronecode/DronecodeSDK.git
   cd DronecodeSDK
   ```
1. Checkout the release/branch you want to build (the `develop` branch is checked out by default).
   * Latest stable build (`master`):
     ```
     git checkout master
     ```
   * Head revision with latest features (`develop`):
     ```
     git checkout develop
     ```
1. Update the submodules:
   ```sh
   git submodule update --init --recursive
   ```
1. Build the (debug) C++ library by calling:
   ```sh
   make default
   ```
   > **Tip** You can build *release* binaries by setting `BUILD_TYPE=Release` as shown below:
     ```sh
     make clean
     BUILD_TYPE=Release make
     ```


1. (Optionally) "Install" the *Dronecode SDK* [as described below](#install-artifacts). This is required in order to build [Dronecode SDK C++ apps](../guide/toolchain.md), but not to run SDK test code.


### Windows

To build the library in Windows, you need:

- [Build Tools for Visual Studio 2017](https://www.visualstudio.com/downloads/#58852): Download and install (only the "Visual C+ Build Tools" are needed from installer).
- [cmake](https://cmake.org/download/): Download the installer and run it. Make sure to tick "add to PATH" during the installation.
- [curl](https://curl.haxx.se/): Download the source, extract and build it, and make the directory of the header files available as described below.

> **Note** The instructions below assume you downloaded [curl-7.56.1.zip](https://curl.haxx.se/download/curl-7.56.1.zip) and extracted to the root of your C drive. You can use a different *curl* if you want.

To build the *Dronecode SDK* C++ Library on Windows:
1. Clone the [Dronecode SDK repository](https://github.com/Dronecode/DronecodeSDK) (or your fork): 
   ```sh
   git clone https://github.com/Dronecode/DronecodeSDK.git
   cd DronecodeSDK
   ```
1. Checkout the release/branch you want to build (the `develop` branch is checked out by default).
   * Latest stable build (`master`):
     ```
     git checkout master
     ```
   * Head revision with latest features (`develop`):
     ```
     git checkout develop
     ```
1. Update the submodules:
   ```sh
   git submodule update --init --recursive
   ```
1. Download the [curl-7.56.1.zip](https://curl.haxx.se/download/curl-7.56.1.zip) source and extract it to the root of your C drive.
1. Open the *VS2015 x64 Native Tools Command Prompt*, go to the source directory and enter:
   ```sh
   cd C:\curl-7.56.1\winbuild
   nmake /f Makefile.vc mode=static VC=15 MACHINE=x64 DEBUG=no
   ```
1. Then build the SDK in Windows:
   ```sh
   cd /your/path/to/DronecodeSDK
   mkdir build && cd build
   cmake -DWIN_CURL_INCLUDE_DIR:STRING=C:\\curl-7.56.1\\include -DWIN_CURL_LIB:STRING="C:\curl-7.56.1\builds\libcurl-vc15-x64-release-static-ipv6-sspi-winssl\lib\libcurl_a.lib" -G "Visual Studio 15 2017 Win64" ..
   cmake --build .
   ```

   > **Tip** You can generate *release* binaries by setting `--config Release` in the build step (`--config Debug` is used by default):
     ```sh
     cmake --build . --config Release
     ```
   <span></span>
   > **Tip** To use more than one CPU core to build set this before building:
     ```sh
     set CL=/MP
     ```

1. (Optionally) "Install" the SDK [as described below](#install-artifacts). This is required in order to build [Dronecode SDK C++ apps](../guide/toolchain.md), but not to run SDK test code.


## Install the SDK {#install-artifacts}

*Installing* builds the SDK **and** copies the libraries and header files into a "public" location so that they can be referenced by C++ applications (see [Building C++ Apps](../guide/toolchain.md)). 
The SDK supports installation system-wide by default. You can also install files locally/relative to the DronecodeSDK tree if needed.

> **Warning** System-wide installation is not yet supported on Windows (see [#155](https://github.com/Dronecode/DronecodeSDK/issues/155)) so you will need to [install the SDK locally](#sdk_local_install).
>
> Windows gurus, we'd [love your help](../README.md#getting-help) to implement this).

### System-wide Install {#sdk_system_wide_install}

System-wide installation copies the SDK headers and binaries to the standard system-wide locations for your platform (On Ubuntu Linux this is **/usr/local/**).

> **Warning** System-wide installation overwrites any previously installed version of the SDK. 

To install the SDK system-wide:

```sh
make clean  #REQUIRED!
make default
sudo make default install  # sudo required to install files to system directories!

# First installation only
sudo ldconfig  # update linker cache
```

> **Note** The first time you build the SDK you may also need to [update the linker cache](http://tldp.org/HOWTO/Program-Library-HOWTO/shared-libraries.html). 
  On Ubuntu this is done with `sudo ldconfig`, as shown above.


### Local Install {#sdk_local_install}

Local installation copies the SDK headers/library to a user-specified location inside the SDK source directory.

On Linux/macOS use the `INSTALL_PREFIX` variable to specify a path relative to the **DronecodeSDK/build/** folder
(or an absolute path).
For example, to install into the **DronecodeSDK/install/** folder you would call:

```sh
make clean  #REQUIRED!
INSTALL_PREFIX=../../install make default install
```

On Windows specify `--target install` when building, as shown:
```sh
cmake --build . --target install
```


## Build for Android

> **Tip** You must first build the C++ Library (as shown above).

To build for Android devices or simulators, you first need to install:
- [Android NDK](https://developer.android.com/ndk/downloads/index.html)
- [Android SDK](https://developer.android.com/studio/index.html)

Also, you need to set these three environment variables:

- `NDK_ROOT` to `<your-android-ndk>`
- `ANDROID_TOOLCHAIN_CMAKE` to `<your-android-ndk>/build/cmake/android.toolchain.cmake`
- `ANDROID_CMAKE_BIN` to `<your-android-sdk>/cmake/<version>/bin/cmake`

E.g. you can add the lines below to your .bashrc, (or .zshrc for zshell users, or .profile):

```sh
export NDK_ROOT=$HOME/Android/android-ndk-r13
export ANDROID_TOOLCHAIN_CMAKE=$HOME/Android/android-ndk-r13/build/cmake/android.toolchain.cmake
export ANDROID_CMAKE_BIN=$HOME/Android/Sdk/cmake/3.6.3155560/bin/cmake
```

Then you build for all Android architectures:
```sh
make android install
```


## Build for iOS

> **Tip** You must first build the C++ Library (as shown above).

To build for real iOS devices on macOS:

```sh
make ios install
```

Build for the iOS simulator on macOS:

```sh
make ios_simulator install
```

## Building in Docker

You can also build the SDK on your host computer with a toolchain running in a [Docker](https://docs.docker.com/) container (this saves you from having to install or manage the toolchain directly). 

> **Tip** There are docker containers based on Fedora and Ubuntu. It doesn't matter which you use!

The main steps are:

1. Install Docker on your host computer
   > **Tip** The easiest way to do this on Ubuntu is to use the [convenience script here](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-convenience-script).
1. Clone the [DronecodeSDK repository](https://github.com/Dronecode/DronecodeSDK) (or your fork) and update the submodules:
   ```sh
   git clone https://github.com/Dronecode/DronecodeSDK.git
   cd DronecodeSDK
   git submodule update --init --recursive
   ```
1. Enter one of the following commands in your host's terminal:
   * Fedora 27 
     ```sh
     docker run --rm -it -v $HOME/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-fedora-27 bash
     ```
   * Fedora 28
     ```sh
     docker run --rm -it -v $HOME/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-fedora-28 bash
     ```
   * Ubuntu 16.04 LTS
     ```sh
     docker run --rm -it -v $HOME/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-ubuntu-16.04 bash 
     ```
   * Ubuntu 18.04 LTS
     ```sh
     docker run --rm -it -v $HOME/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-ubuntu-18.04 bash 
     ```
     
   > **Note** The `-v` flag maps a directory on your host (left side) to a path in the container (right side). 
   > You need to specify the left-side path to the DronecodeSDK repository on your host and the container path must be set as above. 
   > The `--rm` automatically cleans up leftover docker containers after you exit the docker container.

   Docker will download the selected image from [Docker Hub](https://hub.docker.com/u/dronecode/), use it to create a container, and then open a bash prompt:
   ```
   root*81ebe14d0c1a:~/DroneCore#
   ```
1. In the terminal you can build the SDK using the normal Linux `make` commands:
   ```sh
   # Build the C++ library
   make default
   # Build and install the SDK
   make default install
   # Run code-style check
   make fix_style
   # Clean the build
   make clean
   ```

> **Note** Files built in a *Docker* container are owned by root. In order to clean up the **build** and **install** folders you will need to either call `make clean` in the container or `sudo make clean` in the host computer (or `sudo rm -r build`).

### Running Single Docker Commands

You can also run build commands directly from your host (rather than opening bash). Below we show this using the Ubuntu 16.04 docker image:

To make and install the C++ Library:
```bash
docker run --rm -it -v $HOME/<path-to-sdk-repo>/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-ubuntu-16.04 make install
```

To run the code style check:
```bash
docker run --rm -it -v $HOME/<path-to-sdk-repo>/DronecodeSDK:/root/DroneCore:rw dronecode/dronecode-sdk-ubuntu-16.04 make fix_style
```

### Building the Docker Image

The approach above downloads a [container image](https://hub.docker.com/r/dronecode/) from Docker Hub based on Ubuntu 16.04, Ubuntu 18.04, Fedora 27 or Fedora 28. 

You can also build the images yourself using the files in [DronecodeSDK/docker](https://github.com/Dronecode/DronecodeSDK/tree/{{ book.github_branch }}/docker). The image can be used in the same way as the one from Docker Hub.

To build the Ubuntu 16.04 image (the other's follow the same pattern):

1. Open a command prompt/terminal in the root of the SDK source repository.
1. Build the image as shown:
     ```sh
     docker build -f docker/Dockerfile-Ubuntu-16.04 -t my_image .
     ```
   `my_image` can then be used to refer to the image in later steps.
1. Open a bash prompt using the newly created image:
   ```sh
   docker run --rm -it -v $HOME/<path-to-sdk-repo>/DronecodeSDK:/root/DroneCore:rw my_image bash
   ```

## Build SDK Extensions {#sdk_extensions}

The *Dronecode SDK* can be extended with plugins and integration tests that are defined "out of tree". These are declared inside a parallel directory that is included into the SDK at compile time (by specifying `EXTERNAL_DIR` in the `make` command).

The commands to build and install the SDK with an extension library are:
```
make clean   # This is required!
make default EXTERNAL_DIR=relative_path_to_external_directory
sudo make default install
```
See [SDK Extensions](../guide/sdk_extensions.md) for more information.


## Build API Reference Documentation {#build_api_reference}

The C++ source code is annotated using comments using [Doxygen](http://doxygen.nl/manual/index.html) syntax. 

Extract the documentation to markdown files (one per class) on macOS or Linux using the commands:
```bash
rm -R install  # Required (remove previous install/docs)
make distclean     # Required (clean build)
./generate_docs.sh
```
The files are created in **/install/docs/markdown**.

> **Note** Extracting the API reference does not yet work automatically on Windows. 

<span></span>
> **Note** The *generate_docs.sh* script [builds the library](../contributing/build.md), installs it locally to **/install**, and then uses *DOxygen* to create XML documentation in **/install/docs/xml**. 
> The [generate_markdown_from_doxygen_xml.py](https://github.com/Dronecode/DronecodeSDK/blob/{{ book.github_branch }}/generate_markdown_from_doxygen_xml.py) script 
> is then run on all files in the */xml* directory to generate markdown files in **/install/docs/markdown**.

