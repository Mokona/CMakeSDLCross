cmake_minimum_required(VERSION 3.20)
project(CMakeSDLCross)

set(CMAKE_CXX_STANDARD 17)

# Method 1:
# native and cross compiling libraries are both installed system-wide
# find_package(SDL2 REQUIRED) # For method 1
# target_link_libraries(sdl_sample SDL2) # For method 1

# Method 2
# SDL source code (possibly as a submodule) is in the extern/SDL sub-folder

# Not that elegant. Check if there's a better way.
set(MINGW_LIB "")
if (WIN32 AND NOT MSVC)
    set(MINGW_LIB mingw32)
endif()

add_subdirectory(extern/SDL)
add_executable(sdl_sample main.cpp)
# The link order is important for mingw32
target_link_libraries(sdl_sample ${MINGW_LIB} SDL2::SDL2main SDL2::SDL2)
