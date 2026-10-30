#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    ENET_Callbacks.cpp
    ENET_Callbacks.h
    ENET_Compress.cpp
    ENET_Host.cpp
    ENET_List.cpp
    ENET_List.h
    ENET_Packet.cpp
    ENET_Peer.cpp
    ENET_Protocol.cpp
    ENET_Protocol.h
    ENET_Time.h
    ENET_Types.h
    ENET_Unix.cpp
    ENET_Unix.h
    ENET_Utility.h
    ENET_Win32.cpp
    ENET_Win32.h
    enet.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
