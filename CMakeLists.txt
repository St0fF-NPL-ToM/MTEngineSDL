#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL
 ]]
cmake_minimum_required( VERSION 4.2 )

function( bool varName )
    if ( DEFINED ${varName} AND ${varName} )
        set( ${varName} 1 )
     else()
        set( ${varName} 0 )
    endif()
    return( PROPAGATE ${varName} )
endfunction( bool varName )

project( MTEngineSDL LANGUAGES C CXX )

set( CMAKE_CXX_STANDARD 17 )
set( CMAKE_CXX_STANDARD_REQUIRED On )
set( CMAKE_CXX_EXTENSIONS Off )
set( BUILD_SHARED_LIBS off )

# llama.cpp integration
option( MT_ENABLE_LLAMA_CPP "Enable llama.cpp integration" 1 )
option( MT_LLAMA_CUDA "Enable llama.cpp CUDA backend" 0 )
option( MT_LLAMA_VULKAN "Enable llama.cpp Vulkan backend" 0 )
option( MT_ENABLE_MBEDTLS "Enable mbedTLS HTTPS support (cpp-httplib)" 1 )
option( MT_ENABLE_FTXUI "Enable FTXUI terminal UI library" 1 )
option( MT_GGML_NATIVE "Enable native CPU optimizations for ggml (disable for VMs)" 1 )

    # LLAMA is enabled, anyhow, as it vendors stuff
    set( CACHE{LLAMA_BUILD_COMMON} FORCE VALUE on )
    set( CACHE{LLAMA_BUILD_TESTS} FORCE VALUE OFF )
    set( CACHE{LLAMA_BUILD_TOOLS} FORCE VALUE OFF )
    set( CACHE{LLAMA_BUILD_EXAMPLES} FORCE VALUE OFF )
    set( CACHE{LLAMA_BUILD_SERVER} FORCE VALUE OFF )
    set( CACHE{LLAMA_TOOLS_INSTALL} FORCE VALUE OFF )
    set( CACHE{LLAMA_TESTS_INSTALL} FORCE VALUE OFF )
    set( CACHE{GGML_NATIVE} FORCE VALUE ${MT_GGML_NATIVE} )
    set( CACHE{GGML_CUDA} FORCE VALUE ${MT_LLAMA_CUDA} )
    set( CACHE{GGML_VULKAN} FORCE VALUE ${MT_LLAMA_VULKAN} )
    # Build FTXUI as a subproject and package its 3 component static libs into a single archive.
    set( CACHE{FTXUI_BUILD_DOCS} FORCE VALUE OFF )
    set( CACHE{FTXUI_BUILD_EXAMPLES} FORCE VALUE OFF )
    set( CACHE{FTXUI_BUILD_MODULES} FORCE VALUE OFF )
    set( CACHE{FTXUI_BUILD_TESTS} FORCE VALUE OFF )
    set( CACHE{FTXUI_BUILD_TESTS_FUZZER} FORCE VALUE OFF )
    set( CACHE{FTXUI_ENABLE_INSTALL} FORCE VALUE OFF )
    set( CACHE{FTXUI_QUIET} FORCE VALUE ON )

#[[ reduce unwanted (known) warning messages - depends on compiler (clang and gcc share most switches) ]]
if ( "${CMAKE_CXX_COMPILER_ID}" MATCHES "(Clang)|(GNU)" )
    add_compile_options( -fpermissive -Wno-narrowing )
    set( CMAKE_C_OPTIONS "${CMAKE_C_OPTIONS}" -Wno-implicit-function-declaration -Wint-conversion -Wold-style-definition )
endif()

# gather libraries
find_package( SDL2 REQUIRED )
set( MTEngineSDL_LIBRARIES SDL2::SDL2 v4l2 )

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
    GIT_TAG v0.7.0
)
FetchContent_Declare( MbedTLS
    GIT_REPOSITORY https://github.com/Mbed-TLS/mbedtls.git
    GIT_TAG v4.2.0
)
FetchContent_Declare( FTXUI
    GIT_REPOSITORY https://github.com/ArthurSonzogni/FTXUI.git
    GIT_TAG v7.0.3
)
FetchContent_MakeAvailable( LLAMA_CPP )
if ( MT_ENABLE_LLAMA_CPP )
    list( APPEND MTEngineSDL_LIBRARIES llama )
endif()
FetchContent_MakeAvailable( MbedTLS FTXUI )
list( APPEND MTEngineSDL_LIBRARIES cpp-httplib MbedTLS::mbedtls
    ftxui::screen ftxui::dom ftxui::component ftxui::ftxui
)
# compiler defines we know we need in advance:
bool( MT_ENABLE_LLAMA_CPP )
bool( MT_ENABLE_MBEDTLS )
bool( MT_ENABLE_FTXUI )
add_compile_definitions(
    IMGUI_IMPL_OPENGL_LOADER_GL3W
    ENABLE_IMGUI_TEST_ENGINE
    MT_CAMERA_CAPTURE_ENABLED
    MT_ENABLE_LLAMA_CPP=${MT_ENABLE_LLAMA_CPP}
    MT_ENABLE_MBEDTLS=${MT_ENABLE_MBEDTLS}
    MT_ENABLE_FTXUI=${MT_ENABLE_FTXUI}
)
if (MT_LLAMA_CUDA)
    add_compile_definitions(MT_LLAMA_CUDA=1)
endif()
if (MT_LLAMA_VULKAN)
    add_compile_definitions(MT_LLAMA_VULKAN=1)
endif()

#[[ produce the library target ]]
add_library( MTEngineSDL STATIC )

add_subdirectory( src )
add_subdirectory( platform/${MTEngineSDL_PLATFORM} )
add_subdirectory( other/lib )

target_link_libraries( MTEngineSDL PRIVATE ${MTEngineSDL_LIBRARIES} )

function( DirTargets DIR )
    message( "Folder: '${DIR}'" )
    get_directory_property( _p DIRECTORY ${DIR} BUILDSYSTEM_TARGETS )
    message( "  Targets: ${_p}" )
    get_directory_property( _p DIRECTORY ${DIR} IMPORTED_TARGETS )
    message( "  ImportTargets: ${_p}" )
endfunction( DirTargets )

DirTargets( . )
message( "  LinkTargets: ${MTEngineSDL_LIBRARIES}" )
