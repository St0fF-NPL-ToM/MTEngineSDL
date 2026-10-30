#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Platform list for Windows
 ]]
cmake_minimum_required( VERSION 4.2 )

add_subdirectory( "src.Windows" )

file( GLOB_RECURSE PLATFORM_INCLUDES RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "include/*" )

target_include_directories( MTEngineSDL SYSTEM PUBLIC "include" )
target_sources( MTEngineSDL PUBLIC ${PLATFORM_INCLUDES} )
