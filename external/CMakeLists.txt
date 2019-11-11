cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(external-projects LANGUAGES CXX)

set(STAGED_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/stage)
message(STATUS "${PROJECT_NAME} staged install: ${STAGED_INSTALL_PREFIX}")

set_property(DIRECTORY PROPERTY EP_BASE ${CMAKE_BINARY_DIR}/external)

add_subdirectory("googletest")
add_subdirectory("rapidjson")

set(AVS_MINIMUM_REQUIRED 1.13)
add_subdirectory("avs-device-sdk")
