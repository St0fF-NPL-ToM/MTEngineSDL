#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CVideoAudioChannel.cpp
    CVideoAudioChannel.h
    CVideoPlayer.cpp
    CVideoPlayer.h
    CVideoPlayerExample.h
    CVideoYUVShader.cpp
    CVideoYUVShader.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
