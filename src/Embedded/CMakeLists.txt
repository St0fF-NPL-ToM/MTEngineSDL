#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Embedded folder
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    console_inverted_plain_gfx.h
    console_plain_gfx.h
    default_font_fnt.h
    default_font_gfx.h
    gamecontrollerdb_txt_zlib.h
    RES_Embedded.h
    RES_Embedded.cpp
    Fonts/font_inter_bold_italic.cpp
    Fonts/font_inter_bold.cpp
    Fonts/font_inter_italic.cpp
    Fonts/font_inter_regular.cpp
    Fonts/font_jetbrains_mono.cpp
    Fonts/README.md
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
