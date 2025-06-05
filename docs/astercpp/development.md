# Development workflow

The project uses CMake to generate build files for the desired platform.
In most cases you only need a modern C++ compiler and the Arm GNU toolchain
when targeting microcontrollers.

Typical steps to build the firmware from the command line:

```bash
cmake -S . -B build
cmake --build build
```

Unit tests can be executed with CTest once the build directory is configured:

```bash
ctest --test-dir build
```

Documentation is produced with Doxygen and published automatically
when changes are pushed to the main branch.
