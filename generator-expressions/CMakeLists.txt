cmake_minimum_required(VERSION 3.14)
project(ExampleGenerators)
message(STATUS "This message can be seen during generation/configuration")

# toggle which line is commented to see the difference when building the "print" target
add_custom_target(print ${CMAKE_COMMAND} -E echo $<0:hello> $<0:world>)

# add_custom_target(print ${CMAKE_COMMAND} -E echo $<1:hello> $<1:world>)

# add_executable(tgt)
# target_include_directories(tgt PRIVATE /opt/include/$<CXX_COMPILER_ID>)
# This would expand to /opt/include/GNU, /opt/include/Clang, etc.
# depending on the C++ compiler used.
