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

## Compilation for Windows from Ubuntu

  * `sudo apt install mingw-w64`
  * `sudo apt install cmake`
    * or `snap install cmake --classic` to get a recent version

### Build
  * `mkdir build_win`
  * `cd build-win`
  * `cmake -DCMAKE_TOOLCHAIN_FILE=ubuntu-mingw64.cmake  -DCMAKE_BUILD_TYPE=Release` .. (or Debug)
  * `make`

### Run
  * `wine sdl_sample.exe` 

## About the Toolchain File
  * The end of two paths contains a hardcoded version. Can it be made better? 
  * 