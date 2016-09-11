cmake_minimum_required (VERSION 2.8 FATAL_ERROR)
project (CHANGE_ME)

include (CTest)
include (ExternalProject)

set (Catch_PREFIX ${CMAKE_BINARY_DIR}/external/Catch)
ExternalProject_Add(Catch-External
  PREFIX ${Catch_PREFIX}
  GIT_REPOSITORY "https://github.com/philsquared/Catch.git"
  GIT_TAG "35f510545d55a831372d3113747bf1314ff4f2ef"
  UPDATE_COMMAND ""
  CONFIGURE_COMMAND ""
  BUILD_COMMAND ""
  INSTALL_COMMAND ${CMAKE_COMMAND} -E copy
    ${Catch_PREFIX}/src/Catch-External/single_include/catch.hpp
    ${Catch_PREFIX}/include/catch.hpp
)

add_library(Catch INTERFACE)
add_dependencies(Catch Catch-External)
target_include_directories(Catch INTERFACE ${Catch_PREFIX}/include)

enable_testing()
add_executable(test_driver
  tests/test_driver.cpp
  tests/my_awesome_test.cpp
)
target_link_libraries(test_driver Catch)
add_test(NAME MyAwesomeTest COMMAND test_driver)
