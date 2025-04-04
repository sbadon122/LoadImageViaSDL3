cmake_minimum_required(VERSION 3.30)
project(LoadImageViaSDL3)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/$<CONFIGURATION>")

# This assumes the SDL source is available in vendored/SDL
add_subdirectory(vendored/SDL EXCLUDE_FROM_ALL)
add_subdirectory(vendored/SDL_image EXCLUDE_FROM_ALL)

# Create your game executable target as usual
add_executable(LoadImageViaSDL3 main.cpp)

# Link to the actual SDL3 library.
target_link_libraries(LoadImageViaSDL3 SDL3_image::SDL3_image SDL3::SDL3)