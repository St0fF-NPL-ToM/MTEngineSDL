#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    MIDI/CMidiInKeyboard.cpp
    MIDI/CMidiInKeyboard.h
    WAV/SND_WavReader.cpp
    WAV/SND_WavReader.h
    CAudioChannel.cpp
    CAudioChannel.h
    CAudioChannelBusFloat.cpp
    CAudioChannelBusFloat.h
    CAudioChannelBusInt.cpp
    CAudioChannelBusInt.h
    CAudioChannelMusicPlayer.cpp
    CAudioChannelMusicPlayer.h
    CMusicChannel.cpp
    CMusicChannel.h
    CMusicWaveformCache.h
    CPianoKeyboard.cpp
    CPianoKeyboard.h
    CPlaylistPlaybackManager.cpp
    CPlaylistPlaybackManager.h
    CSlrMusicCueTransitionPlanner.cpp
    CSlrMusicCueTransitionPlanner.h
    CSlrMusicFile.cpp
    CSlrMusicFile.h
    CSlrMusicFileOgg.cpp
    CSlrMusicFileOgg.h
    CSlrMusicPlaylistController.cpp
    CSlrMusicPlaylistController.h
    CSlrMusicPlaylistPersistence.cpp
    CSlrMusicPlaylistPersistence.h
    CSlrMusicSwitcher.cpp
    CSlrMusicSwitcher.h
    SND_Main.cpp
    SND_Main.h
    SND_SoundEngine.cpp
    SND_SoundEngine.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} MIDI WAV )
