#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    png.c
    png.h
    pngconf.h
    pngdebug.h
    pngerror.c
    pngget.c
    pnginfo.h
    pnglibconf.h
    pngmem.c
    pngpread.c
    pngpriv.h
    pngread.c
    pngrio.c
    pngrtran.c
    pngrutil.c
    pngset.c
    pngstruct.h
    pngtrans.c
    pngwio.c
    pngwrite.c
    pngwtran.c
    pngwutil.c
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
