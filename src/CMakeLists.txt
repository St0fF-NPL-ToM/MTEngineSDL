#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    src base folder
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC MT_API.h MT_VERSION.h )
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} Engine )
add_subdirectory( "Embedded" )
add_subdirectory( "Engine/Audio" )
add_subdirectory( "Engine/Core" )
add_subdirectory( "Engine/Funct" )
add_subdirectory( "Engine/GUI" )
add_subdirectory( "Engine/Libs" )
add_subdirectory( "Engine/Sci/Llama" )
add_subdirectory( "Engine/Tests" )
add_subdirectory( "Engine/Tools" )
# add_subdirectory( "Engine/Video" )
