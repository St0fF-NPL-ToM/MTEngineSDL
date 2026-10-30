#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CAssetServer.cpp
    CAssetServer.h
    CAssetServerProcess.cpp
    CAssetServerProcess.h
    CAuthServiceProcess.cpp
    CAuthServiceProcess.h
    CAuthServiceServer.cpp
    CAuthServiceServer.h
    CChatHistory.cpp
    CChatHistory.h
    CClusterConfig.cpp
    CClusterConfig.h
    CDownloadTracker.cpp
    CDownloadTracker.h
    CFileDownloader.cpp
    CFileDownloader.h
    CGameServerProcessBase.cpp
    CGameServerProcessBase.h
    CGameServerRegistry.cpp
    CGameServerRegistry.h
    CLobbyLink.cpp
    CLobbyLink.h
    CLobbyServiceServer.cpp
    CLobbyServiceServer.h
    CNetGameClient.cpp
    CNetGameClient.h
    CNetGameDataProvider.cpp
    CNetGameDataProvider.h
    CNetGameDataProviderLocalFiles.cpp
    CNetGameDataProviderLocalFiles.h
    CNetGameInternalAuth.h
    CNetGamePackets.cpp
    CNetGamePackets.h
    CNetGameServer.cpp
    CNetGameServer.h
    CNetGameUserProfile.cpp
    CNetGameUserProfile.h
    CNetLobbyClient.cpp
    CNetLobbyClient.h
    CNetLobbyClientCallback.h
    CNetLobbyServer.cpp
    CNetLobbyServer.h
    CNodeAgent.cpp
    CNodeAgent.h
    CRegistryClient.cpp
    CRegistryClient.h
    CRegistryServer.cpp
    CRegistryServer.h
    CServerGame.cpp
    CServerGame.h
    CServerGamesManagerBase.cpp
    CServerGamesManagerBase.h
    CSnapshotStorage.cpp
    CSnapshotStorage.h
    CTurnBasedGameServer.cpp
    CTurnBasedGameServer.h
    CViewGameClient.cpp
    CViewGameClient.h
    CViewGameServer.cpp
    CViewGameServer.h
    CViewServerAdmin.cpp
    CViewServerAdmin.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
