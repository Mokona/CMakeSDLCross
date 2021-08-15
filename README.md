# CMakeSDLCross

Tests are made from Ubuntu 20.04.

## Compilation for Ubuntu

### Prerequisites

  * `sudo apt install build-essential`
  * `sudo apt install libsdl2-dev`
  * `sudo apt install cmake`
    * or `snap install cmake --classic` to get a recent version
    
### Build
  * `mkdir build`
  * `cd build`
  * `cmake -DCMAKE_BUILD_TYPE=Release` .. (or Debug)
  * `make`

### Run
  * `./sdl_sample` 

### Thoughts

The Ubuntu version is build against system-wide installed libraries. It's ok
as long as the objective is to build and run locally.

## Compilation for Windows from Ubuntu

  * `sudo apt install mingw-w64`
  * `sudo apt install cmake`
    * or `snap install cmake --classic` to get a recent version

### Build
  * `mkdir build_win`
  * `cd build-win`
  * `cmake -DCMAKE_TOOLCHAIN_FILE=ubuntu-mingw64.cmake  -DCMAKE_BUILD_TYPE=Release` .. (or Debug)
  * `make` **DOES NOT WORK SMOOTHLY YET**

### Run
  * `wine sdl_sample.exe` 

### Thoughts

The cross-compilation needs a SDL version compiled for the target system.

#### Method 1

Use the provided pre-compiled release on the [SDL2](https://libsdl.org) site
(for example `SDL2-devel-2.0.16-mingw.tar.gz`).

The main problem with this prebuilt release is that it's made to be installed
system-wide, but without being packaged.

#### Method 2

Extract SDL sources in the extern folder and use `add_subdirectory`.

## About the Toolchain File
  * The end of two paths contains a hardcoded version. Can it be made better? 
  