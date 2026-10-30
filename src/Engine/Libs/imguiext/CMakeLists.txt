#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    dirent_portable.h
    IconsFontAwesome_c.h
    IconsKenney_c.h
    IconsMaterialDesign_c.h
    imgui_markdown.h
    imgui_md.cpp
    imgui_md.h
    imgui_memory_editor.h
    imgui_stdlib.cpp
    imgui_stdlib.h
    imgui_toggle.cpp
    imgui_toggle.h
    imguial_button.h
    imguial_fonts.cpp
    imguial_fonts.h
    imguial_log.cpp
    imguial_log.h
    imguial_term.cpp
    imguial_term.h
    imguiComboFilter.cpp
    imguiComboFilter.h
    imguifilesystem.cpp
    imguifilesystem.h
    imguihelper.cpp
    imguihelper.h
    ImGuiToolbar.h
    ImGuiUtils.h
    imspinner.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
