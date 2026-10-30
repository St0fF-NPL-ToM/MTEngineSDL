#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    ContinuousParam/CContinuousParam.cpp
    ContinuousParam/CContinuousParam.h
    ContinuousParam/CContinuousParamBezier.cpp
    ContinuousParam/CContinuousParamBezier.h
    ContinuousParam/CContinuousParamLinear.cpp
    ContinuousParam/CContinuousParamLinear.h
    ContinuousParam/CContinuousParamSin.cpp
    ContinuousParam/CContinuousParamSin.h
    ContinuousParam/CContinuousParamSinHalf.cpp
    ContinuousParam/CContinuousParamSinHalf.h
    DataTable/CDataTable.cpp
    DataTable/CDataTable.h
    DataTable/CGuiViewDataTable.cpp
    DataTable/CGuiViewDataTable.h
    DataTable/FUN_CSVParser.cpp
    DataTable/FUN_CSVParser.h
    FFT/rad2fft.cpp
    FFT/rad2fft.h
    FFT/SpectrumAnalysis.cpp
    FFT/SpectrumAnalysis.h
    ImageProcessing/CImageKernel.cpp
    ImageProcessing/CImageKernel.h
    ImageProcessing/IMG_Filters.cpp
    ImageProcessing/IMG_Filters.h
    ImageProcessing/IMG_HoughLines.cpp
    ImageProcessing/IMG_HoughLines.h
    ImageProcessing/IMG_Scale.cpp
    ImageProcessing/IMG_Scale.h
    ImageProcessing/IMG_SimpleSegmentation.cpp
    ImageProcessing/IMG_SimpleSegmentation.h
    ImageProcessing/resampler/resampler.cpp
    ImageProcessing/resampler/resampler.h
    ImageProcessing/stb_image/stb_image.c
    ImageProcessing/stb_image/stb_image.h
    CCombinations.h
    CFeatureConfig.cpp
    CFeatureConfig.h
    CHjsonSerializer.cpp
    CHjsonSerializer.h
    FUN_GenerateSinTab.cpp
    FUN_GenerateSinTab.h
    FUN_IntervalTree.cpp
    FUN_IntervalTree.h
    std_membuf.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    ContinuousParam
    DataTable
    FFT
    ImageProcessing
    ImageProcessing/resampler
    ImageProcessing/stb_image
)
