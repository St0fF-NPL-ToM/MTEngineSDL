#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    thirdparty/stb/imstb_image_write.h
    thirdparty/Str/Str.h
    imgui_capture_tool.cpp
    imgui_capture_tool.h
    imgui_te_context.cpp
    imgui_te_context.h
    imgui_te_coroutine.cpp
    imgui_te_coroutine.h
    imgui_te_engine.cpp
    imgui_te_engine.h
    imgui_te_exporters.cpp
    imgui_te_exporters.h
    imgui_te_imconfig.h
    imgui_te_internal.h
    imgui_te_perftool.cpp
    imgui_te_perftool.h
    imgui_te_ui.cpp
    imgui_te_ui.h
    imgui_te_utils.cpp
    imgui_te_utils.h
    LICENSE.txt
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} thirdparty thirdparty/stb thirdparty/Str )
