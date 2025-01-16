cmake_minimum_required(VERSION 3.14)  # FetchContent requires at least CMake 3.14
project(MyProject)

# Enable FetchContent module
include(FetchContent)

set(GLSLANG_ENABLE_INSTALL ON)
set(ENABLE_OPT OFF)
FetchContent_Declare(
  glslang
  GIT_REPOSITORY git@github.com:vikke1234/glslang.git
  GIT_TAG        main
  OVERRIDE_FIND_PACKAGE
)

FetchContent_MakeAvailable(glslang)
find_package(glslang)

add_executable(sample src/main.cpp)
target_link_libraries(sample glslang)

