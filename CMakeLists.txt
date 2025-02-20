cmake_minimum_required(VERSION 3.10)

project(Utest LANGUAGES C CXX)

add_library(Utest INTERFACE)

target_include_directories(Utest INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
)

# Install rules
install(TARGETS Utest EXPORT UtestConfig)

# Export the package for use with FetchContent
export(EXPORT UtestConfig
    FILE "${CMAKE_CURRENT_BINARY_DIR}/UtestConfig.cmake"
    NAMESPACE Utest::
)
