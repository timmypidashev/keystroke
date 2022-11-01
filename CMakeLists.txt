# Set cmake_minimum_required
# --------------------------
cmake_minimum_required(VERSION 3.23)

# Set C++ 20 Standard
# ----------------------------------
set(CMAKE_CXX_STANDARD 20)

# Set cmake compiler
# ----------------------------------
set(CMAKE_CXX_COMPILER "clang++")

# Configure cmake
# ----------------------------------
list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/CMake")
set_property(GLOBAL PROPERTY USE_FOLDERS ON)	

# Set project
# --------------------------
project(keystroke
    VERSION
        0.1.0
    DESCRIPTION
        "A keylogger that defends its user."
    HOMEPAGE_URL
        "https://github.com/timmypidashev/keystroke"
    LANGUAGES
        C CXX
)

# Configure Header Files
# ----------------------------------
configure_file (
  "${PROJECT_SOURCE_DIR}/version.h.in"
  "${PROJECT_BINARY_DIR}/version.h"
)

# Allow 'config.h' to be used throughout the program
# ----------------------------------
include_directories(${PROJECT_BINARY_DIR})

# Set executable output directory
# ----------------------------------
set(EXECUTABLE_OUTPUT_PATH "${CMAKE_BINARY_DIR}")

# Create executable
# ----------------------------------
add_executable(${PROJECT_NAME} main.cpp)