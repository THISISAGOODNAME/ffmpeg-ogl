add_library(FFmpeg INTERFACE IMPORTED GLOBAL)

target_include_directories(FFmpeg INTERFACE ffmpeg-master-latest-win64-gpl-shared/include)

target_link_directories(FFmpeg INTERFACE ffmpeg-master-latest-win64-gpl-shared/lib)
target_link_libraries(FFmpeg INTERFACE
    avcodec
    avdevice
    avfilter
    avformat
    avutil
    swresample
    swscale
    )
