#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for Linux
 ]]
cmake_minimum_required( VERSION 4.2 )

set( PLATFORM_DIR "src.Linux/" )
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
list( TRANSFORM PLATFORM_SOURCES PREPEND ${PLATFORM_DIR} )
list( TRANSFORM PLATFORM_SOURCES APPEND ".h" OUTPUT_VARIABLE PLATFORM_HEADERS )
list( TRANSFORM PLATFORM_SOURCES APPEND ".cpp" )
list( APPEND PLATFORM_HEADERS
    ${PLATFORM_DIR}nfd/ftg_core.h
    ${PLATFORM_DIR}nfd/simple_exec.h
)
list( APPEND PLATFORM_SOURCES
    ${PLATFORM_DIR}nfd/nfd_zenity.c
    ${PLATFORM_DIR}gl3w.c
    ${PLATFORM_DIR}main.cpp
)
file( GLOB_RECURSE PLATFORM_INCLUDES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "${PLATFORM_DIR}include/*" )

target_include_directories( MTEngineSDL SYSTEM PUBLIC "${PLATFORM_DIR}include" )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_SOURCES} ${PLATFORM_HEADERS} ${PLATFORM_INCLUDES} )
