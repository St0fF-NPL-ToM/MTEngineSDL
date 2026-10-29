#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL
 ]]
cmake_minimum_required( VERSION 4.2 )

project( MTEngineSDL LANGUAGES C CXX )

set( CMAKE_CXX_STANDARD 17 )
set( CMAKE_CXX_STANDARD_REQUIRED On )
set( CMAKE_CXX_EXTENSIONS Off )
set( BUILD_SHARED_LIBS off )

#[[ reduce unwanted (known) warning messages - depends on compiler (clang and gcc share most switches) ]]
if ( "${CMAKE_CXX_COMPILER_ID}" MATCHES "(Clang)|(GNU)" )
    add_compile_options( -fpermissive -Wno-narrowing  -Wno-implicit-function-declaration" -Wint-conversion" )
endif()

# gather libraries
find_package( SDL2 REQUIRED )
set( MTEngineSDL_LIBRARIES SDL2::SDL2 )

#[[ do that platform-dependent stuff once, if possible ]]
if ( LINUX )
    message( NOTICE "Compiling on Linux" )
    set( MTEngineSDL_PLATFORM Linux )
    add_compile_definitions( LINUX )
    # linux-specific libraries
    find_package( PkgConfig REQUIRED )
    pkg_check_modules( GTK3 REQUIRED IMPORTED_TARGET GLOBAL gtk+-3.0 )
    list( APPEND MTEngineSDL_LIBRARIES PkgConfig::GTK3 )
elseif( APPLE )
    message( NOTICE "Compiling on Apple" )
    set( MTEngineSDL_PLATFORM MacOS )
    add_compile_definitions( MACOS )
elseif( WIN32 )
    message( NOTICE "Compiling on Windows" )
    set( MTEngineSDL_PLATFORM Windows )
endif()
# continue library gathering by simply pulling ready-made CMake Libs:
include( FetchContent )
FetchContent_Declare( LLAMA_CPP
    GIT_REPOSITORY https://github.com/ggml-org/llama.cpp
    GIT_TAG v0.8.0
)
FetchContent_Declare( MBEDTLS
    GIT_REPOSITORY https://github.com/Mbed-TLS/mbedtls.git
    GIT_TAG v4.2.0
)
FetchContent_Declare( FTXUI
    GIT_REPOSITORY https://github.com/ArthurSonzogni/FTXUI.git
    GIT_TAG v7.0.3
)
FetchContent_MakeAvailable( LLAMA_CPP MBEDTLS FTXUI )
list( APPEND MTEngineSDL_LIBRARIES
    llama
    ftxui::screen ftxui::dom ftxui::component ftxui::ftxui
)
# compiler defines we know we need in advance:
add_compile_definitions(
    IMGUI_IMPL_OPENGL_LOADER_GL3W
    ENABLE_IMGUI_TEST_ENGINE
    MT_CAMERA_CAPTURE_ENABLED
)

#[[ produce the library target ]]
add_library( MTEngineSDL STATIC )
target_link_libraries( MTEngineSDL PRIVATE ${MTEngineSDL_LIBRARIES} )

add_subdirectory( src )
add_subdirectory( platform/${MTEngineSDL_PLATFORM} )
add_subdirectory( other/lib )
