#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CInterruptibleSleep.cpp
    CInterruptibleSleep.h
    CProcessSpawner.cpp
    CProcessSpawner.h
    CTask.cpp
    CTask.h
    CTaskScheduler.cpp
    CTaskScheduler.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
add_subdirectory( NetGame )
# add_subdirectory( Undo )
