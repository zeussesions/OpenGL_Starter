cmake_minimum_required(VERSION 3.5.0)
project(first_opengl_project)

find_package(OpenGL REQUIRED)

link_directories("/opt/homebrew/lib")
include_directories(
    "/opt/homebrew/include"
    "lib/glad/include"
)

add_executable(first_opengl_project 
    src/main.cpp
    lib/glad/include/glad/glad.h
    lib/glad/src/glad.c
)
target_link_libraries(first_opengl_project glfw OpenGL::GL)
