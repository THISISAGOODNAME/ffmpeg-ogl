cmake_minimum_required(VERSION 3.20)

project(video-ogl)

# glfw
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)
add_subdirectory(3rd_party/glfw)

# ffmpeg
add_subdirectory(3rd_party/ffmpeg)

# openGL
find_package(OpenGL REQUIRED)

add_executable(video_ogl main.cpp video_reader.cpp video_reader.h)
target_link_libraries(video_ogl FFmpeg glfw OpenGL::GL OpenGL::GLU)
