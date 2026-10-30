#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CGuiMain.cpp
    CGuiMain.h
    COneTouchData.cpp
    COneTouchData.h
    GUI_Main.cpp
    GUI_Main.h
    GuiConsts.h
    AudioMixer/CViewAudioMixer.cpp
    AudioMixer/CViewAudioMixer.h
    Fonts/CGuiFontManager.cpp
    Fonts/CGuiFontManager.h
    Layout/CLayoutManager.cpp
    Layout/CLayoutManager.h
    Layout/CLayoutParameter.cpp
    Layout/CLayoutParameter.h
    Waveform/CMusicWaveformCache.cpp
    Waveform/CMusicWaveformCache.h
    Waveform/CViewWaveform.cpp
    Waveform/CViewWaveform.h
    Waveform/CWaveformData.cpp
    Waveform/CWaveformData.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} AudioMixer Fonts Layout Waveform )
add_subdirectory( Controls )
add_subdirectory( Helpers )
