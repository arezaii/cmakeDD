cmake_minimum_required(VERSION 3.15)
set(CMAKE_VERBOSE_MAKEFILE ON)
project(hello-cmake CXX)
add_executable(hello hello.cpp)
set_property(TARGET hello PROPERTY CXX_STANDARD 17)
# behavior changed in 3.22.0 and then fixed/changed in 3.22.2
# see https://cmake.org/cmake/help/git-stage/policy/CMP0128.html#policy:CMP0128