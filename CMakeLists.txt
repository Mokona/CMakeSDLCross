cmake_minimum_required(VERSION 3.20)
project(CMakeSDLCross)

set(CMAKE_CXX_STANDARD 17)

# find_package(SDL2 REQUIRED) # For method 1
add_subdirectory(extern/SDL) # For method 2

add_executable(sdl_sample main.cpp)

# target_link_libraries(sdl_sample SDL2) # For method 1
target_link_libraries(sdl_sample SDL2::SDL2main SDL2::SDL2) # For method 2
