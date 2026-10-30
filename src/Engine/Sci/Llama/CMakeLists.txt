#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CLlamaModelDownloader.cpp
    CLlamaModelDownloader.h
    CLlamaModelManager.cpp
    CLlamaModelManager.h
    CLlamaPromptAgent.cpp
    CLlamaPromptAgent.h
    CLlamaService.cpp
    CLlamaService.h
    CLlamaStreamParser.h
    CLlamaTask.h
    CLlamaTaskQueue.cpp
    CLlamaTaskQueue.h
    CLlamaTypes.h
    llama_cpp_version.h
    LLamaBackend_LlamaCpp.cpp
    LLamaBackend_LlamaCpp.h
    LLamaBackend_Stub.cpp
    LLamaBackend_Stub.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
