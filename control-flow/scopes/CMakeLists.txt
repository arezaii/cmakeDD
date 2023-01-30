cmake_minimum_required(VERSION 3.14)


set(Name Douglas)
message("root directory: before adding Matryoshka subdirectory, name is ${Name}")

add_subdirectory(Matryoshka)

message("root directory: after adding Matryoshka subdirectory, name is ${Name}")
