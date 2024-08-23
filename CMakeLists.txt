cmake_minimum_required(VERSION 3.10 FATAL_ERROR)

set(PROJECT_NAME cGame)

project (${PROJECT_NAME})

add_executable(${PROJECT_NAME} src/main.cpp)

add_subdirectory(external/glfw)
add_subdirectory(external/glad)

include_directories(${GLFW_INCLUDE_DIR})
target_link_libraries(${PROJECT_NAME} glfw glad)
find_package(OpenGL REQUIRED)
target_link_libraries(${PROJECT_NAME} OpenGL::GL)

