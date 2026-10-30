#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder … MAIN Engine folder:
    - any engine parts that are larger than ~10 files get their own CML file
      → those are integrated at the end of the file by running add_subdirectory
    - others are listed here, alphabetically sorted to ease the task of maintenance
      → add all headers and sources relative to ${CMAKE_CURRENT_SOURCE_DIR} to the lib using
        target_sources
      → include all folders containing headers via target_include_directories
 ]]
cmake_minimum_required( VERSION 4.2 )
# this does not work, yet.  No idea how Slajerek had meant this httplib to be …
    if ( llama_cpp_SOURCE_DIR AND EXISTS "${llama_cpp_SOURCE_DIR}" )
        file( COPY_FILE "${llama_cpp_SOURCE_DIR}/vendor/cpp-httplib/httplib.h" httplib/l_httplib.h )
        file( COPY_FILE "${llama_cpp_SOURCE_DIR}/vendor/cpp-httplib/httplib.cpp" httplib/l_httplib_vendor.cpp )
    endif()

target_sources( MTEngineSDL PUBLIC
    crow/crow_all.h
    hjson/hjson_decode.cpp
    hjson/hjson_encode.cpp
    hjson/hjson_parsenumber.cpp
    hjson/hjson_value.cpp
    hjson/hjson.h
    httplib/httplib.h
    httplib/httplib_vendor.cpp
    imgui-notify/fa_solid_900.cpp
    imgui-notify/fa_solid_900.h
    imgui-notify/font_awesome_5.h
    imgui-notify/imgui_notify.h
    imgui-notify/tahoma.h
    implot/implot_colors_extension.cpp
    implot/implot_colors_extension.h
    implot/implot_demo.cpp
    implot/implot_internal.h
    implot/implot_items.cpp
    implot/implot.cpp
    implot/implot.h
    imterm/misc.hpp
    imterm/terminal.hpp
    libtmt/tmt.c
    libtmt/tmt.h
    lodepng/lodepng.h
    lodepng/lodepng.cpp
    stb/stb_sprintf.cpp
    stb/stb_sprintf.h
    md5/MD5_Defs.h
    md5/MD5.cpp
    md5/MD5.h
    minizip/crypt.h
    minizip/ioapi.c
    minizip/ioapi.h
    minizip/mztools.c
    minizip/mztools.h
    minizip/unzip.c
    minizip/unzip.h
    minizip/zip.c
    minizip/zip.h
    mtrand/MTH_MTRand.cpp
    mtrand/MTH_MTRand.h
    mtrand/mtrand.cpp
    mtrand/mtrand.h
    nfd/nfd_common.c
    nfd/nfd_common.h
    nfd/nfd.h
    nlohmann/FUN_ConvertHjsonToJson.cpp
    nlohmann/FUN_ConvertHjsonToJson.h
    nlohmann/json_fwd.hpp
    nlohmann/json.hpp
    pugixml/pugiconfig.h
    pugixml/pugixml.cpp
    pugixml/pugixml.h
    rtmidi/RtMidi.cpp
    rtmidi/RtMidi.h
    sgSHA256/sgSHA256.cpp
    sgSHA256/sgSHA256.h
    utf8/utf8_checked.h
    utf8/utf8_core.h
    utf8/utf8_unchecked.h
    utf8/utf8.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    basis_universal
    crow
    hjson
    httplib
    imgui-notify
    implot
    imterm
    libtmt
    lodepng
    md4c
    md5
    minizip
    mtrand
    nestegg
    nestegg/nestegg
    nfd
    nlohmann
    pugixml
    rtmidi
    sgSHA256
    stb
    utf8
)
foreach( _sd IN ITEMS
    basis_universal/transcoder
    basis_universal/zstd
    ENet
    imgui
    imgui_test_engine
    imguiext
    jpeg
    libjson
    libopus/opus
    libpng
    libvpx/vpx
    tremor
    uWebSockets
    zlib
)
    add_subdirectory( ${_sd} )
endforeach()
