cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(googletest-download NONE)

message(STATUS "Will download and build googletest 1.8.0")

include(ExternalProject)
ExternalProject_Add(googletest
  URL
    https://github.com/google/googletest/archive/release-1.8.0.tar.gz
  URL_HASH
    SHA256=58a6f4277ca2bc8565222b3bbd58a177609e9c488e8a72649359ba51450db7d8
  DOWNLOAD_NO_PROGRESS
    1
  CMAKE_ARGS
    -DBUILD_GTEST=ON
    -DBUILD_GMOCK=ON
    -DCMAKE_INSTALL_PREFIX=${STAGED_INSTALL_PREFIX}
  TEST_COMMAND
    ""
)
