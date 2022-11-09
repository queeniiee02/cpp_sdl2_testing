cmake_minimum_required(VERSION 3.20)
project(cpp_sdl2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")


find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS} ${SDL2_IMAGE_INCLUDE_DIRS})


 set(SDL_H /opt/homebrew/Cellar/sdl2/2.24.2/include)
 set(SDL_H_IMAGE /opt/homebrew/Cellar/sdl2_image/2.6.2/include)
 
 include_directories(${SDL_H} ${SDL_H_IMAGE})
 
 set(SDL_LIB /opt/homebrew/Cellar/sdl2/2.24.2/lib/libSDL2-2.0.0.dylib)
 set(SDL_IMAGE_LIB /opt/homebrew/Cellar/sdl2/2.24.2/lib/libSDL2-2.0.0.dylib)
 link_libraries(${SDL_LIB} ${SDL_IMAGE_LIB})

add_executable(cpp_sdl2 src/main.cpp)
target_link_libraries(cpp_sdl2 ${SDL2_LIBRARIES} ${SDL2_IMAGE_INCLUDE_DIRS} ${SDL_IMAGE_LIB})
