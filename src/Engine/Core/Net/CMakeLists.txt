#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CNetClient.cpp
    CNetClient.h
    CNetClientData.cpp
    CNetClientData.h
    CNetPacket.cpp
    CNetPacket.h
    CNetServer.cpp
    CNetServer.h
    NET_AuthPw2.h
    NET_Includes.h
    NET_Main.cpp
    NET_Main.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
