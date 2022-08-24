cmake_minimum_required(VERSION 3.23)
project(hello_world)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(FindPkgConfig)
pkg_check_modules(MIRAL miral REQUIRED)

add_executable(hello_world main.cpp)

target_include_directories(hello_world PUBLIC SYSTEM ${MIRAL_INCLUDE_DIRS})
target_link_libraries(     hello_world               ${MIRAL_LDFLAGS})
