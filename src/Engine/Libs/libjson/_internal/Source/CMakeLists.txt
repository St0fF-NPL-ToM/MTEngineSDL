#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    internalJSONNode.cpp
    internalJSONNode.h
    JSON_Base64.h
    JSONAllocator.cpp
    JSONAllocator.h
    JSONChildren.cpp
    JSONChildren.h
    JSONDebug.cpp
    JSONDebug.h
    JSONDefs.h
    JSONGlobals.h
    JSONIterators.cpp
    JSONMemory.cpp
    JSONMemory.h
    JSONMemoryPool.h
    JSONNode_Mutex.cpp
    JSONNode.cpp
    JSONNode.h
    JSONPreparse.cpp
    JSONPreparse.h
    JSONSharedString.h
    JSONSingleton.h
    JSONStats.h
    JSONStream.cpp
    JSONStream.h
    JSONValidator.cpp
    JSONValidator.h
    JSONWorker.cpp
    JSONWorker.h
    JSONWriter.cpp
    libjson.cpp
    NumberToString.h
    JSONDefs/GNU_C.h
    JSONDefs/Strings_Defs.h
    JSONDefs/Unknown_C.h
    JSONDefs/Visual_C.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} JSONDefs )
