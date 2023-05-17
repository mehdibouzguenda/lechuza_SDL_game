cmake_minimum_required(VERSION 3.25)
project(witch)

set(CMAKE_C_STANDARD 11 )



# Find SDL 1.2 library
find_package(SDL REQUIRED)
include_directories(${SDL_INCLUDE_DIR})

# Add the path to SDL_gfx library
include_directories(/usr/include/SDL)

# Find SDL_image library
find_package(SDL_image REQUIRED)
include_directories(${SDL_IMAGE_INCLUDE_DIRS})

# Add include directories
include_directories(${SDL_INCLUDE_DIRS})

include_directories(cmake-build-debug/fonts)
include_directories(cmake-build-debug/image)
include_directories(cmake-build-debug/music)
find_package(SDL_ttf REQUIRED)
include_directories(${SDL_TTF_INCLUDE_DIRS})

add_executable(witch

        debut.c
        debut.h
        enig.h
        enigf.c
        enigme.c
        enigme.h
        enigmefichier.c
        enigmefihier.h
        fonction.c
        fonction.h
        intro.c
        intro.h
        main.c
        multi.c
        multi.h
        option.c
        option.h
        sound.c
        sound.h
        stage1.c
        stage1.h
        stage1s.c
        stage2.c
        stage2.h
        stage2s.c
        )


target_link_libraries(witch  ${SDL_LIBRARY} SDL_gfx ${SDL_IMAGE_LIBRARIES} SDL_mixer ${SDL_TTF_LIBRARIES})