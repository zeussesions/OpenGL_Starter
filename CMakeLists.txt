cmake_minimum_required(VERSION 3.10)
project(OpenGL)

set(CMAKE_CXX_STANDARD 11)

# Set the path to the GLFW and GLEW library and include directories
set(GLFW_INCLUDE_DIR "/opt/homebrew/Cellar/glfw/3.3.8/include")
set(GLFW_LIBRARY_DIR "/opt/homebrew/Cellar/glfw/3.3.8/lib")

set(GLEW_INCLUDE_DIR "/opt/homebrew/Cellar/glew/2.2.0_1/include")
set(GLEW_LIBRARY_DIR "/opt/homebrew/Cellar/glew/2.2.0_1/lib")

# Find GLFW and GLEW
find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)

# Include GLFW and GLEW headers
include_directories(
    ${GLFW_INCLUDE_DIRS}
    ${GLEW_INCLUDE_DIRS}
)

# Set the source files for your project
set(SOURCES
    src/main.cpp
    # Add your other source files here
)

# Set the header files for your project
set(HEADERS
    # Add your header files here
)

# Create the executable
add_executable(OpenGL ${SOURCES} ${HEADERS})

# Link GLFW, OpenGL, and GLEW libraries
target_link_libraries(OpenGL PRIVATE glfw OpenGL::GL GLEW::GLEW)
