#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for MacOS
 ]]
cmake_minimum_required( VERSION 4.2 )

set( PLATFORM_DIR "src.MacOS/" )
set( PLATFORM_SOURCES
    CCameraMacOS
    CSlrFileFromDocuments
    CSlrFileFromOS
    CSlrFileFromResources
    CSlrFileFromTemp
    DBG_Log
    SYS_FileSystem
    SYS_Memory
    SYS_Platform
    SYS_SharedMemory
    SYS_MacOS
    SYS_MacOSWrapper
)
list( TRANSFORM PLATFORM_SOURCES PREPEND ${PLATFORM_DIR} )
list( TRANSFORM PLATFORM_SOURCES APPEND ".h" OUTPUT_VARIABLE PLATFORM_HEADERS )
list( TRANSFORM PLATFORM_SOURCES APPEND ".mm" )
list( APPEND PLATFORM_HEADERS
    ${PLATFORM_DIR}MacOS_Wrapper.h
)
list( APPEND PLATFORM_SOURCES
    ${PLATFORM_DIR}nfd_cocoa.m
    ${PLATFORM_DIR}gl3w.mm
    ${PLATFORM_DIR}main.mm
)
file( GLOB_RECURSE PLATFORM_INCLUDES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "${PLATFORM_DIR}include/*" )

target_include_directories( MTEngineSDL SYSTEM PUBLIC "${PLATFORM_DIR}include" )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_SOURCES} ${PLATFORM_HEADERS} ${PLATFORM_INCLUDES} )
