cmake_minimum_required (VERSION 3.13)

set (CMAKE_BUILD_TYPE Release CACHE STRING "Build type")

project(dlib-cmake-example)


find_package (dlib 19.8 CONFIG REQUIRED)
message (STATUS "Found dlib: ${dlib_DIR} (found version ${dlib_VERSION})")

add_executable(optim_ex optimization_ex.cpp)
target_link_libraries(optim_ex PRIVATE dlib::dlib)

add_library(foo foo.cpp)
target_link_libraries(foo PRIVATE dlib::dlib)
