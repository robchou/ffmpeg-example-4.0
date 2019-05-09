cmake_minimum_required(VERSION 2.8)
project(ffmpeg-examples)

find_package(PkgConfig REQUIRED)
pkg_check_modules(FFMPEG REQUIRED libavcodec libavformat libavutil libswscale libswresample libavfilter)

include_directories(
    ${FFMPEG_INCLUDE_DIRS}
    )

link_directories(
    ${FFMPEG_LIBRARY_DIRS}
    )

set(ffmpeg_example_source_files
    avio_dir_cmd.c
    avio_reading.c
    decode_audio.c
    decode_video.c
    demuxing_decoding.c
    encode_audio.c
    encode_video.c
    extract_mvs.c
    filter_audio.c
    filtering_audio.c
    filtering_video.c
    http_multiclient.c
    hw_decode.c
    metadata.c
    muxing.c
    #qsvdec.c
    remuxing.c
    resampling_audio.c
    scaling_video.c
    transcode_aac.c
    transcoding.c
    )
foreach(example ${ffmpeg_example_source_files})
    string(REPLACE ".c" "" exec ${example})
    add_executable(${exec} ${example})
    target_link_libraries(${exec}
        ${FFMPEG_LIBRARIES}
        sndio
        asound
        pthread
        dl
        va
        z
        m
        )
endforeach()
