cmake_minimum_required(VERSION 3.24)
project(iRonXtra LANGUAGES CXX)

add_executable(iRonXtra
    iFL03.rc
    AppControl.cpp
    Config.cpp
    GuiCEF.cpp
    iracing.cpp
    Logger.cpp
    main.cpp
    Overlay.cpp
    OverlayDebug.cpp
    preview_mode.cpp
    stub_data.cpp
    WinMainShim.cpp
    irsdk/irsdk_client.cpp
    irsdk/irsdk_utils.cpp
    irsdk/yaml_parser.cpp
)

target_compile_features(iRonXtra
    PUBLIC
        cxx_std_20
)

target_include_directories(iRonXtra
    PUBLIC
        
)

target_compile_definitions(iRonXtra
    PUBLIC
        $<$<CONFIG:Debug>:_DEBUG>
        $<$<CONFIG:Release>:NDEBUG>
        PICOJSON_USE_RVALUE_REFERENCE=0
)

target_link_directories(iRonXtra
    PUBLIC
        "C:/Program Files (x86)/Windows Kits/10/Lib/10.0.26100.0/um/x64"
)

target_link_libraries(iRonXtra
    PUBLIC
        kernel32.lib
        user32.lib
        gdi32.lib
        winspool.lib
        comdlg32.lib
        advapi32.lib
        shell32.lib
        ole32.lib
        oleaut32.lib
        uuid.lib
        odbc32.lib
        odbccp32.lib
        DXGI.lib
        d2d1.lib
        D3D11.lib
        Dcomp.lib
        Dwrite.lib
)

target_compile_options(iRonXtra
    PUBLIC
)

