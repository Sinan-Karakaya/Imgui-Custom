cmake_minimum_required(VERSION 3.22)
project(Imgui-Custom)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")

find_package(glfw3 3.3 REQUIRED)
include_directories(${GLFW_INCLUDE_DIRS})
find_package(OpenGL REQUIRED
        COMPONENTS OpenGL)
include_directories(${OPENGL_INCLUDE_DIR})

include_directories(include)
add_executable(Imgui-Custom main.cpp)

add_subdirectory(lib/imgui)
add_dependencies(Imgui-Custom imgui)
add_dependencies(Imgui-Custom glfw)

target_link_libraries(Imgui-Custom imgui)
target_link_libraries(Imgui-Custom glfw)
target_link_libraries(Imgui-Custom ${OPENGL_LIBRARIES})
