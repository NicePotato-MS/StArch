# Some of this stuff sorta taken from TIC-80 but also sorta not
# This doesn't work right now, I have only just started

cmake_minimum_required(VERSION 3.28)
include(cmake/version.cmake)
project(StArch VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_REVISION} LANGUAGES C CXX)

# Add C source files
set(SOURCES src/main.c)

# Detect platform
if(WIN32)
    message("Detected platform: Windows")
    add_definitions(-DPLATFORM_WINDOWS)
elseif(APPLE)
    message("Detected platform: macOS")
    add_definitions(-DPLATFORM_MACOS)
elseif(UNIX)
    message("Detected platform: Unix/Linux")
    add_definitions(-DPLATFORM_UNIX)
endif()

# Add executable
add_executable(${PROJECT_NAME} ${SOURCES})
