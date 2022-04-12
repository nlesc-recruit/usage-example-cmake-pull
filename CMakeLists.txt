cmake_minimum_required(VERSION 3.17 FATAL_ERROR)

project(
  vector_add_example
  DESCRIPTION "Example using C++ Wrappers for the CUDA Driver API"
  VERSION 0.0.1
  HOMEPAGE_URL https://github.com/nlesc-recruit/usage-example-git-submodules
  LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_BUILD_TYPE Release)

# Use CMAKE_INSTALL_PREFIX when searching for libraries to run the installed
# vector_add_example program.
include(GNUInstallDirs)
list(APPEND CMAKE_INSTALL_RPATH ${CMAKE_INSTALL_FULL_LIBDIR})

# Download cudawrappers from GitHub
include(FetchContent)
FetchContent_Declare(
  cudawrappers
  GIT_REPOSITORY https://github.com/nlesc-recruit/cudawrappers
  GIT_TAG 8ccbc24037c2e2fcbb66ecb6e63ef0b739da2276)
FetchContent_MakeAvailable(cudawrappers)

add_executable(vector_add_example vector_add.cpp)

target_link_libraries(vector_add_example PRIVATE cudawrappers::cu
                                                 cudawrappers::nvrtc)

install(TARGETS vector_add_example)
