cmake_minimum_required(VERSION 3.17)
project(FFmpeg_Tutorial C)

set(CMAKE_C_STANDARD 11)

if (NOT ${SDL_FOUND})
    message(FATAL_ERROR "SDL Not found.")
endif ()

include_directories(FFmpeg2.5/include)
include_directories(${SDL_INCLUDE_DIR})
link_directories(FFmpeg2.5/lib)


link_libraries(
        avcodec
        avformat
        avutil
        swscale
        swresample
        bz2
        iconv
        lzma
        z
        "-framework CoreFoundation"
        "-framework CoreVideo"
        "-framework VideoDecodeAcceleration"
        ${SDL_LIBRARY}
)

add_executable(Tutorial01 tutorial01.c)
add_executable(Tutorial02 tutorial02.c)
add_executable(Tutorial03 tutorial03.c)
add_executable(Tutorial04 tutorial04.c)
add_executable(Tutorial05 tutorial05.c)
add_executable(Tutorial06 tutorial06.c)
add_executable(Tutorial07 tutorial07.c)
