#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

set( SRC
    CRenderBackend.cpp
    CRenderBackend.h
#    CRenderBackendOpenGL3.cpp
#    CRenderBackendOpenGL3.h
    CRenderBackendOpenGL4.cpp
    CRenderBackendOpenGL4.h
    CRenderShader.cpp
    CRenderShader.h
    CRenderShaderMaskedTile.cpp
    CRenderShaderMaskedTile.h
    CRenderShaderMaskedTileQueued.cpp
    CRenderShaderMaskedTileQueued.h
    CRenderShaderOpenGL4.cpp
    CRenderShaderOpenGL4.h
    CRenderShaderOpenGL4ShaderToy.cpp
    CRenderShaderOpenGL4ShaderToy.h
    EImageGpuFormat.h
    VID_Blits.cpp
    VID_Blits.h
    VID_ImageBinding.cpp
    VID_ImageBinding.h
    VID_Main.cpp
    VID_Main.h
)
if ( APPLE )
    list( APPEND SRC
        CRenderBackendMetal.h
        CRenderBackendMetal.mm
    )
endif()
target_sources( MTEngineSDL PUBLIC ${SRC} )
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
