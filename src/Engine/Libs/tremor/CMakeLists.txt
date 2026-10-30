#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    config-tremor.h
    tremor-asm_arm.h
    tremor-backends.h
    tremor-block.c
    tremor-block.h
    tremor-codebook.c
    tremor-codebook.h
    tremor-codec_internal.h
    tremor-floor0.c
    tremor-floor1.c
    tremor-info.c
    tremor-ivorbiscodec.h
    tremor-ivorbisfile.h
    tremor-lsp_lookup.h
    tremor-mapping0.c
    tremor-mdct_lookup.h
    tremor-mdct.c
    tremor-mdct.h
    tremor-misc.h
    tremor-os.h
    tremor-registry.c
    tremor-registry.h
    tremor-res012.c
    tremor-sharedbook.c
    tremor-synthesis.c
    tremor-vorbisfile.c
    tremor-window_lookup.h
    tremor-window.c
    tremor-window.h
    Ogg/bitwise.c
    Ogg/framing.c
    Ogg/ogg.h
    Ogg/tremor-os_types.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} Ogg )
