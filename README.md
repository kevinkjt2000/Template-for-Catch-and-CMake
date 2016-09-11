## Synopsis

This project is a template for adding the C++ Catch testing framework to new or existing CMake projects.

## Requirements

* CMake >= 2.8
* C++ compiler/IDE

## Instructions

* Clone this repository if starting a fresh project, or simply cut-and-paste what you need from the CMakeLists.txt file if adding to an existing project.
* Run CMake as you usually would to generate the build files for your favorite compiler/IDE.  For example, run `mkdir build && cd build && cmake ..` from the directory containing CMakeLists.txt.
* Execute `ctest --test-command` or `ctest --build-and-test` to run the test executables that are added by CMakeLists.txt.  You can also invoke tests by using the appropriate IDE or makefile target, but using the ctest command works across all CMake generators.
