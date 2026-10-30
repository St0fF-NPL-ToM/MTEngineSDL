#[[
    This is the new approach of trying to create a cross-platform
    buildsystem for MTEngineSDL

    Engine folder …
 ]]
cmake_minimum_required( VERSION 4.2 )

target_sources( MTEngineSDL PUBLIC
    CColorsTheme.cpp                CColorsTheme.h
    CGuiBackground.cpp              CGuiBackground.h
    CGuiButton.cpp                  CGuiButton.h
    CGuiButtonMenu.cpp              CGuiButtonMenu.h
    CGuiButtonSwitch.cpp            CGuiButtonSwitch.h
    CGuiButtonText.cpp              CGuiButtonText.h
    CGuiEditBoxFloat.cpp            CGuiEditBoxFloat.h
    CGuiEditBoxHex.cpp              CGuiEditBoxHex.h
    CGuiEditBoxInt.cpp              CGuiEditBoxInt.h
    CGuiEditBoxText.cpp             CGuiEditBoxText.h
    CGuiEditHex.cpp                 CGuiEditHex.h
    CGuiElement.cpp                 CGuiElement.h
    CGuiEvent.cpp                   CGuiEvent.h
    CGuiFolderFavorite.h
    CGuiLabel.cpp                   CGuiLabel.h
    CGuiList.cpp                    CGuiList.h
    CGuiListTree.cpp                CGuiListTree.h
    CGuiRadio.cpp                   CGuiRadio.h
    CGuiRichTextLabel.cpp           CGuiRichTextLabel.h
    CGuiSlider.cpp                  CGuiSlider.h
    CGuiTheme.cpp                   CGuiTheme.h
    CGuiView.cpp                    CGuiView.h
    CGuiViewFade.cpp                CGuiViewFade.h
    CGuiViewFrame.cpp               CGuiViewFrame.h
    CGuiViewHorizontalScroll.cpp    CGuiViewHorizontalScroll.h
    CGuiViewList.cpp                CGuiViewList.h
    CGuiViewMenu.cpp                CGuiViewMenu.h
    CGuiViewMessageBox.cpp          CGuiViewMessageBox.h
    CGuiViewMovingPane.cpp          CGuiViewMovingPane.h
    CGuiViewMovingPaneImage.cpp     CGuiViewMovingPaneImage.h
    CGuiViewNumKeys.cpp             CGuiViewNumKeys.h
    CGuiViewSaveFile.cpp            CGuiViewSaveFile.h
    CGuiViewSelectFile.cpp          CGuiViewSelectFile.h
    CGuiViewSelectFolder.cpp        CGuiViewSelectFolder.h
    CGuiViewSplit4.cpp              CGuiViewSplit4.h
    CGuiViewTerminal.cpp            CGuiViewTerminal.h
    CGuiViewToolBox.cpp             CGuiViewToolBox.h
    CGuiViewVerticalScroll.cpp      CGuiViewVerticalScroll.h
    CGuiViewWindowsManager.cpp      CGuiViewWindowsManager.h
    CGuiWindow.cpp                  CGuiWindow.h
)
target_include_directories( MTEngineSDL PUBLIC ${CMAKE_CURRENT_SOURCE_DIR} )
