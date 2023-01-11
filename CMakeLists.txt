cmake_minimum_required(VERSION 3.16)
project(video-app C CXX)
set(CMAKE_CXX_STANDARD 17)

# Deps
# meta (graphics)
add_subdirectory(lib/metal)  

# ffmpeg
add_subdirectory(lib/FFmpeg)

list(APPEND SOURCES
    src/main.cpp
)

add_executable(video-app MACOSX_BUNDLE ${SOURCES})

target_link_libraries(video-app METAL_CPP)
