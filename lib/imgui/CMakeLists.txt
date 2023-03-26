cmake_minimum_required(VERSION 3.22)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_FLAGS "-Wall -Wextra -fdiagnostics-color=always -fno-gnu-unique")
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)

file(GLOB_RECURSE SOURCES *.cpp)
add_library(imgui STATIC ${SOURCES})

target_include_directories(imgui PRIVATE ${PROJECT_SOURCE_DIR}/include)
