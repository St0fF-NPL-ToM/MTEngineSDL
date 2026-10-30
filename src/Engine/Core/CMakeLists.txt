#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CByteBuffer.cpp
    CByteBuffer.h
    CCameraCapture.cpp
    CCameraCapture.h
    CCombinations.h
    CConfigStorage.cpp
    CConfigStorage.h
    CConfigStorageHjson.cpp
    CConfigStorageHjson.h
    CDataAdapter.cpp
    CDataAdapter.h
    CGlobalDropFileCallback.h
    CGlobalKeyboardCallback.h
    CGlobalLayoutCallback.h
    CGlobalLogicCallback.h
    CGlobalOSWindowChangedCallback.h
    CI18nManager.cpp
    CI18nManager.h
    CImageData.cpp
    CImageData.h
    ConstantsAndMacros.h
    CSlrAnimation.cpp
    CSlrAnimation.h
    CSlrAnimationState.cpp
    CSlrAnimationState.h
    CSlrDate.cpp
    CSlrDate.h
    CSlrFile.cpp
    CSlrFile.h
    CSlrFileFromMemory.cpp
    CSlrFileFromMemory.h
    CSlrFileMemory.cpp
    CSlrFileMemory.h
    CSlrFileZlib.cpp
    CSlrFileZlib.h
    CSlrFont.cpp
    CSlrFont.h
    CSlrFontBitmap.cpp
    CSlrFontBitmap.h
    CSlrFontProportional.cpp
    CSlrFontProportional.h
    CSlrImage.cpp
    CSlrImage.h
    CSlrImageBase.cpp
    CSlrImageBase.h
    CSlrImageMask.cpp
    CSlrImageMask.h
    CSlrImageTexture.cpp
    CSlrImageTexture.h
    CSlrKeyboardShortcuts.cpp
    CSlrKeyboardShortcuts.h
    CSlrResourceBase.cpp
    CSlrResourceBase.h
    CSlrString.cpp
    CSlrString.h
    CSlrTextParser.cpp
    CSlrTextParser.h
    CSlrTexture.cpp
    CSlrTexture.h
    CSystemFileDialogCallback.cpp
    CSystemFileDialogCallback.h
    DBG_LogForCWrapper.cpp
    DBG_LogForCWrapper.h
    GFX_Types.h
    ILogSink.h
    M_Circlebuf.h
    MTH_FastMath.cpp
    MTH_FastMath.h
    MTH_FastMathSinTab.h
    MTH_FixedPoint_SinTab.h
    MTH_FixedPoint.cpp
    MTH_FixedPoint.h
    MTH_FixedPointUtils.h
    MTH_Random.cpp
    MTH_Random.h
    RES_DeployFile.cpp
    RES_DeployFile.h
    RES_ResourceManager.cpp
    RES_ResourceManager.h
    SYS_CommandLine.cpp
    SYS_CommandLine.h
    SYS_Crypto.h
    SYS_DefaultConfig.cpp
    SYS_DefaultConfig.h
    SYS_Defs.h
    SYS_DocsVsRes.h
    SYS_Funct.cpp
    SYS_Funct.h
    SYS_KeyCodes.cpp
    SYS_KeyCodes.h
    SYS_Main.cpp
    SYS_Main.h
    SYS_PauseResume.cpp
    SYS_PauseResume.h
    SYS_PIPE.cpp
    SYS_PIPE.h
    SYS_SecureRandom.h
    SYS_Startup.cpp
    SYS_Startup.h
    SYS_Threading.cpp
    SYS_Threading.h
    SYS_Types.h
    VID_Fonts.cpp
    VID_Fonts.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )

add_subdirectory( GamePads )
add_subdirectory( Net )
add_subdirectory( Pool )
add_subdirectory( Render )
