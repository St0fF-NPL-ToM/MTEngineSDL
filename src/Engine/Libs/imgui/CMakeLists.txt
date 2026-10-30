#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    imconfig.h
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_freetype.cpp
    imgui_freetype.h
    imgui_impl_opengl3_loader.h
    imgui_impl_opengl3.cpp
    imgui_impl_opengl3.h
    imgui_impl_sdl2.cpp
    imgui_impl_sdl2.h
    imgui_internal.h
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui.cpp
    imgui.h
    imstb_rectpack.h
    imstb_textedit.h
    imstb_truetype.h
    README.md
)
if ( APPLE )
    target_sources( MTEngineSDL PUBLIC
        imgui_impl_metal.h
        imgui_impl_metal.mm
    )
endif()
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
