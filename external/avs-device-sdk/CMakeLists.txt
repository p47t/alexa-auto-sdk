cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(avs-device-sdk-download NONE)

message(STATUS "Will download and build AVS 1.13")

include(ExternalProject)
ExternalProject_Add(avs-device-sdk
  DEPENDS
    googletest
    rapidjson
  URL
    https://github.com/alexa/avs-device-sdk/archive/v1.13.tar.gz
  URL_HASH
    SHA256=cc103422471d1b436f15081c52960540f11d3278409495e7b2d2ffd44bff10a2
  DOWNLOAD_NO_PROGRESS
    1
  UPDATE_COMMAND
    ""
  CMAKE_ARGS
    -DCMAKE_CXX_COMPILER=${CMAKE_CXX_COMPILER}
    -DCMAKE_CXX_STANDARD=${CMAKE_CXX_STANDARD}
    -DCMAKE_CXX_EXTENSIONS=${CMAKE_CXX_EXTENSIONS}
    -DCMAKE_CXX_STANDARD_REQUIRED=${CMAKE_CXX_STANDARD_REQUIRED}
    -DCMAKE_INSTALL_PREFIX=${STAGED_INSTALL_PREFIX}
    -DOPUS=ON
  CMAKE_CACHE_ARGS
    -DCMAKE_CXX_FLAGS:STRING=${CMAKE_CXX_FLAGS}
  )

