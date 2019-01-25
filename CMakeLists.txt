cmake_minimum_required(VERSION 3.2)
project(ffmpeg-examples)

set(ffmpeg_libs
    avdevice
    avformat
    avfilter
    avcodec
    swresample
    swscale
    avutil
    m
   )


add_executable(avio_dir_cmd avio_dir_cmd.c)
target_link_libraries(avio_dir_cmd ${ffmpeg_libs})

add_executable(avio_reading avio_reading.c)
target_link_libraries(avio_reading ${ffmpeg_libs})

add_executable(decode_audio decode_audio.c)
target_link_libraries(decode_audio ${ffmpeg_libs})

add_executable(decode_video decode_video.c)
target_link_libraries(decode_video ${ffmpeg_libs})

add_executable(demuxing_decoding demuxing_decoding.c)
target_link_libraries(demuxing_decoding ${ffmpeg_libs})

add_executable(encode_audio encode_audio.c)
target_link_libraries(encode_audio ${ffmpeg_libs})

add_executable(encode_video encode_video.c)
target_link_libraries(encode_video ${ffmpeg_libs})

add_executable(extract_mvs extract_mvs.c)
target_link_libraries(extract_mvs ${ffmpeg_libs})

add_executable(filtering_video filtering_video.c)
target_link_libraries(filtering_video ${ffmpeg_libs})

add_executable(filtering_audio filtering_audio.c)
target_link_libraries(filtering_audio ${ffmpeg_libs})

add_executable(http_multiclient http_multiclient.c)
target_link_libraries(http_multiclient ${ffmpeg_libs})

add_executable(hw_decode hw_decode.c)
target_link_libraries(hw_decode ${ffmpeg_libs})

add_executable(metadata metadata.c)
target_link_libraries(metadata ${ffmpeg_libs})

add_executable(muxing muxing.c)
target_link_libraries(muxing ${ffmpeg_libs})

add_executable(remuxing remuxing.c)
target_link_libraries(remuxing ${ffmpeg_libs})

add_executable(resampling_audio resampling_audio.c)
target_link_libraries(resampling_audio ${ffmpeg_libs})

add_executable(scaling_video scaling_video.c)
target_link_libraries(scaling_video ${ffmpeg_libs})

add_executable(transcode_aac transcode_aac.c)
target_link_libraries(transcode_aac ${ffmpeg_libs})

add_executable(transcoding transcoding.c)
target_link_libraries(transcoding ${ffmpeg_libs})
