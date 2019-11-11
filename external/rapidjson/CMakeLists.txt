cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(rapidjson-download NONE)

message(STATUS "Will download and build rapidjson 1.1.0")

include(ExternalProject)
ExternalProject_Add(rapidjson
  URL
    https://github.com/Tencent/rapidjson/archive/v1.1.0.tar.gz
  URL_HASH
    SHA256=bf7ced29704a1e696fbccf2a2b4ea068e7774fa37f6d7dd4039d0787f8bed98e
  DOWNLOAD_NO_PROGRESS
    1
  CONFIGURE_COMMAND
    ""
  BUILD_COMMAND
    ""
  INSTALL_COMMAND
    ${CMAKE_COMMAND} -E copy_directory <SOURCE_DIR>/include/rapidjson ${STAGED_INSTALL_PREFIX}/include/rapidjson
  TEST_COMMAND
    ""
)
