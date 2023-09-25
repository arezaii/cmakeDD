This reproducer is to demonstrate the behavior shift from CMake version 3.21 to
3.22.0, and then again at 3.22.2.

Prior to 3.22.0, using set_property(TARGET hello PROPERTY CXX_STANDARD 17)
would cause the -std=gnu++17 flag to be added to the compilation flags.
From 3.22.0 to 3.22.2, that doesn't happen, the flag just never gets added.

See https://cmake.org/cmake/help/git-stage/policy/CMP0128.html#policy:CMP0128
for more information on the policy and https://cmake.org/cmake/help/git-stage/release/3.22.html#cmake-3-22-release-notes for info on the behavior change/fix.


To reproduce the issue you can get older versions of cmake from https://cmake.org/files/.

Download any version prior to 3.22.0, and either v3.22.0 or v3.22.1, and v3.22.2

Set up is to use this project in different terminals. Setup one terminal to use
the oldest version, one to use either 3.22.0 or 3.22.1, and one to use 3.22.2.

In each terminal:
```
export VERBOSE=1
cmake --version
cmake -B build .
cmake --build build
```

In the versions besides the affected versions (3.22.0, 3.22.1), you will see
the flag `-std=gnu++17` added to the compilation flags for `hello.cpp`. In the
affected versions, you will not.
