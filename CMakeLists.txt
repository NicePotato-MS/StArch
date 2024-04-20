# Most of this stuff is taken from TIC-80
# This doesn't work right now, I have only just started

cmake_minimum_required(VERSION 3.28)
include(cmake/version.cmake)
project(StArch VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_REVISION} LANGUAGES C CXX)

message("Building for target: ${CMAKE_SYSTEM_NAME}")
message("PROJECT_VERSION: ${PROJECT_VERSION}${VERSION_STATUS}")

option(BUILD_SDL "SDL Enabled" ON)
option(BUILD_SDLGPU "SDL GPU Enabled" OFF)

if(NOT BUILD_SDL)
    set(BUILD_SDLGPU OFF)
endif()

message("BUILD_SDLGPU: ${BUILD_SDLGPU}")

include(cmake/sdl.cmake)
