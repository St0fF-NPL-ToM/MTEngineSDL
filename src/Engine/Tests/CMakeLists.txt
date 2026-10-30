#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    src base folder
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CImGuiTestEngine.cpp
    CImGuiTestEngine.h
    CTest.cpp
    CTest.h
    CTestI18nEngine.cpp
    CTestI18nEngine.h
    CTestLlamaAvailability.cpp
    CTestLlamaAvailability.h
    CTestRunner.cpp
    CTestRunner.h
    CTestSuite.cpp
    CTestSuite.h
    ITestCallback.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
