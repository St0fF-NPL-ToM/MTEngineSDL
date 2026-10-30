#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    basisu_astc_hdr_core.h
    basisu_astc_helpers.h
    basisu_containers_impl.h
    basisu_containers.h
    basisu_file_headers.h
    basisu_idct.h
    basisu_transcoder_internal.h
    basisu_transcoder_uastc.h
    basisu_transcoder.cpp
    basisu_transcoder.h
    basisu.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
