cmake_minimum_required(VERSION 3.20)

project(TXT_text-editor LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(WX_ROOT "${CMAKE_SOURCE_DIR}/third_party/wxWidgets")

find_program(WX_CONFIG_EXECUTABLE
    NAMES wx-config
    PATHS
        "${WX_ROOT}/bin"
    NO_DEFAULT_PATH
    REQUIRED
)

set(wxWidgets_CONFIG_EXECUTABLE "${WX_CONFIG_EXECUTABLE}")

# Find wxWidgets components
find_package(wxWidgets REQUIRED COMPONENTS core base)

message(STATUS "wxWidgets version: ${wxWidgets_VERSION}")
message(STATUS "wxWidgets working ")

include(${wxWidgets_USE_FILE})

# Executable
add_executable(txt main.cpp)

target_link_libraries(txt PRIVATE
    ${wxWidgets_LIBRARIES}
)

