This reproducer is to demonstrate the behavior shift from CMake version 3.21 to
3.22.0, and then again at 3.22.2.

Prior to 3.22.0, using set_property(TARGET hello PROPERTY CXX_STANDARD 17)
would cause the -std=gnu++17 flag to be added to the compilation flags.
From 3.22.0 to 3.22.2, that doesn't happen, the flag just never gets added.

See https://cmake.org/cmake/help/git-stage/policy/CMP0128.html#policy:CMP0128
for more information on the policy and https://cmake.org/cmake/help/git-stage/release/3.22.html#cmake-3-22-release-notes for info on the behavior change/fix.