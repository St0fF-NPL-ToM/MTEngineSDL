#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    vp8.h
    vp8cx.h
    vp8dx.h
    vpx_codec.h
    vpx_decoder.h
    vpx_encoder.h
    vpx_ext_ratectrl.h
    vpx_frame_buffer.h
    vpx_image.h
    vpx_integer.h
    vpx_tpl.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
