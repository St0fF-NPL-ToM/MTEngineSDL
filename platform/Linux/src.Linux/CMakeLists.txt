#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for Linux
 ]]
cmake_minimum_required( VERSION 4.2 )

set( PLATFORM_SOURCES
    CCameraLinux
    CSlrFileFromDocuments
    CSlrFileFromOS
    CSlrFileFromResources
    CSlrFileFromTemp
    DBG_Log
    SYS_FileSystem
    SYS_Memory
    SYS_Platform
    SYS_SharedMemory
    SYS_LinuxWrapper
)
list( TRANSFORM PLATFORM_SOURCES APPEND ".h" OUTPUT_VARIABLE PLATFORM_HEADERS )
list( TRANSFORM PLATFORM_SOURCES APPEND ".cpp" )
list( APPEND PLATFORM_HEADERS
    nfd/ftg_core.h
    nfd/simple_exec.h
)
list( APPEND PLATFORM_SOURCES
    nfd/nfd_zenity.c
    gl3w.c
    main.cpp
)

file( GLOB_RECURSE PLATFORM_INCLUDES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "include/*" )

target_include_directories( MTEngineSDL SYSTEM PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}" "include" "nfd" )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_SOURCES} ${PLATFORM_HEADERS} ${PLATFORM_INCLUDES} )
