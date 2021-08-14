cmake_minimum_required(VERSION 3.20)
project(CMakeSDLCross)

set(CMAKE_CXX_STANDARD 17)

find_package(SDL2 REQUIRED)

add_executable(sdl_sample main.cpp)
target_link_libraries(sdl_sample SDL2)