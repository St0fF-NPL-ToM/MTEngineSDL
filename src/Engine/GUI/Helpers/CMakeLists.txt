#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CGuiViewConsole.cpp
    CGuiViewConsole.h
    CGuiViewDebugLog.cpp
    CGuiViewDebugLog.h
    CGuiViewDummy.cpp
    CGuiViewDummy.h
    CGuiViewDummySimple.cpp
    CGuiViewDummySimple.h
    CGuiViewImageWithLayer.cpp
    CGuiViewImageWithLayer.h
    CGuiViewLlamaChat.cpp
    CGuiViewLlamaChat.h
    CGuiViewLlamaModelLoader.cpp
    CGuiViewLlamaModelLoader.h
    CGuiViewMessages.cpp
    CGuiViewMessages.h
    CGuiViewMusicPlaylist.cpp
    CGuiViewMusicPlaylist.h
    CGuiViewProgressBarWindow.cpp
    CGuiViewProgressBarWindow.h
    CGuiViewSearch.cpp
    CGuiViewSearch.h
    CGuiViewTableItem.cpp
    CGuiViewTableItem.h
    CGuiViewTableWithFilterAndButtons.cpp
    CGuiViewTableWithFilterAndButtons.h
    CGuiViewUiDebug.cpp
    CGuiViewUiDebug.h
    CRecentlyOpenedFiles.cpp
    CRecentlyOpenedFiles.h
    CViewCamera.cpp
    CViewCamera.h
    CViewLlamaTaskQueue.cpp
    CViewLlamaTaskQueue.h
    GUI_Debug.cpp
    GUI_Debug.h
    LoadingScreen/CGuiViewBaseLoadingScreen.cpp
    LoadingScreen/CGuiViewBaseLoadingScreen.h
    LoadingScreen/CGuiViewLoadingScreen.cpp
    LoadingScreen/CGuiViewLoadingScreen.h
    ResourceManager/CGuiViewBaseResourceManager.cpp
    ResourceManager/CGuiViewBaseResourceManager.h
    ResourceManager/CGuiViewResourceManager.cpp
    ResourceManager/CGuiViewResourceManager.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} LoadingScreen ResourceManager )
