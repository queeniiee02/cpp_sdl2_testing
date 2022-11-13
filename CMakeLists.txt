
######
# macOS version
######

cmake_minimum_required(VERSION 3.20)
project(cpp_sdl2)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")


find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_mixer REQUIRED)
find_package(SDL2_ttf REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS} ${SDL2_IMAGE_INCLUDE_DIRS} ${SDL2_MIXER_INCLUDE_DIRS} ${SDL2_TTF})


set(SDL_H /opt/homebrew/Cellar/sdl2/2.24.2/include)
set(SDL_H_IMAGE /opt/homebrew/Cellar/sdl2_image/2.6.2/include)
set(SDL_H_MIXER /opt/homebrew/Cellar/sdl2_mixer/2.6.2/include)
set(SDL_H_MIXER /opt/homebrew/Cellar/sdl2_ttf/2.20.1/include)
 
include_directories(${SDL_H} ${SDL_H_IMAGE} ${SDL_H_MIXER} ${SDL_H_TTF})

set(SDL_LIB /opt/homebrew/Cellar/sdl2/2.24.2/lib/libSDL2-2.0.0.dylib)
set(SDL_IMAGE_LIB /opt/homebrew/Cellar/sdl2_image/2.6.2/lib/libSDL2_image-2.0.0.dylib)
set(SDL_MIXER_LIB /opt/homebrew/Cellar/sdl2_mixer/2.6.2/lib/libSDL2_mixer-2.0.0.dylib)
set(SDL_MIXER_LIB /opt/homebrew/Cellar/sdl2_ttf/2.20.1/lib/libSDL2_ttf-2.0.0.dylib)
link_libraries(${SDL_LIB} ${SDL_IMAGE_LIB} ${SDL_MIXER_LIB} ${SDL_TTF_LIB})

add_executable(cpp_sdl2 src/main.cpp)
add_executable(cpp_sdl2_gog src/gog.cpp)
target_link_libraries(cpp_sdl2 ${SDL2_LIBRARIES} ${SDL_IMAGE_LIB} ${SDL_MIXER_LIB} ${SDL_TTF_LIB})
target_link_libraries(cpp_sdl2_gog ${SDL2_LIBRARIES} ${SDL_IMAGE_LIB} ${SDL_MIXER_LIB} ${SDL_TTF_LIB})
