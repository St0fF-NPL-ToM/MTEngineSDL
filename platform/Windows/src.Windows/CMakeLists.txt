#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for Windows
 ]]
cmake_minimum_required( VERSION 4.2 )

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
list( TRANSFORM PLATFORM_SOURCES APPEND ".h" OUTPUT_VARIABLE PLATFORM_HEADERS )
list( TRANSFORM PLATFORM_SOURCES APPEND ".cpp" )
list( APPEND PLATFORM_HEADERS
    dirent.h
    getopt.h
    libgen.h
    main.h
    mman.h
    snprintf.h
    unistd.h
)
list( APPEND PLATFORM_SOURCES
    getopt.c
    gl3w.c
    main.cpp
    mman.c
    nfd_win.cpp
)
target_include_directories( MTEngineSDL SYSTEM PUBLIC "${CMAKE_CURRENT_SOURCE_DIR} )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_SOURCES} ${PLATFORM_HEADERS} )
