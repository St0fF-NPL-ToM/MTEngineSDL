#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for Windows
 ]]
cmake_minimum_required( VERSION 4.2 )

set( PLATFORM_DIR "src.Windows/" )
set( PLATFORM_SOURCES
    CCameraWindows
    CLogByteBuffer
    CSlrFileFromDocuments
    CSlrFileFromOS
    CSlrFileFromResources
    CSlrFileFromTemp
    CSlrFontSystem
    DBG_ConStream
    DBG_Log
    SYS_FileSystem
    SYS_Memory
    SYS_Platform
    SYS_SharedMemory
    SYS_MiniDump
    win-gettimeofday
    win-registry
    win-usleep
)
list( TRANSFORM PLATFORM_SOURCES PREPEND ${PLATFORM_DIR} )
list( TRANSFORM PLATFORM_SOURCES APPEND ".h" OUTPUT_VARIABLE PLATFORM_HEADERS )
list( TRANSFORM PLATFORM_SOURCES APPEND ".cpp" )
list( APPEND PLATFORM_HEADERS
    ${PLATFORM_DIR}dirent.h
    ${PLATFORM_DIR}getopt.h
    ${PLATFORM_DIR}libgen.h
    ${PLATFORM_DIR}main.h
    ${PLATFORM_DIR}mman.h
    ${PLATFORM_DIR}snprintf.h
    ${PLATFORM_DIR}unistd.h
)
list( APPEND PLATFORM_SOURCES
    ${PLATFORM_DIR}getopt.c
    ${PLATFORM_DIR}gl3w.c
    ${PLATFORM_DIR}main.cpp
    ${PLATFORM_DIR}mman.c
    ${PLATFORM_DIR}nfd_win.cpp
)
file( GLOB_RECURSE PLATFORM_INCLUDES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "${PLATFORM_DIR}include/*" )

target_include_directories( MTEngineSDL SYSTEM PUBLIC "${PLATFORM_DIR}include" )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_SOURCES} ${PLATFORM_HEADERS} ${PLATFORM_INCLUDES} )
