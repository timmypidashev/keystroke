# Set cmake_minimum_required
# --------------------------
cmake_minimum_required(VERSION 3.23)

# Set C++ 20 Standard
# ----------------------------------
set(CMAKE_CXX_STANDARD 20)

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
