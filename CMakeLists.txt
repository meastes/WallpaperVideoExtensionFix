cmake_minimum_required(VERSION 3.29)
project(WallpaperVideoExtensionFix)

set(CMAKE_CXX_STANDARD 20)

# Set the project to be a macOS application bundle
set(CMAKE_MACOSX_BUNDLE TRUE)
set(CMAKE_MACOSX_BUNDLE_GUI_APP FALSE)

# Specify that we want to create a universal binary
set(CMAKE_OSX_ARCHITECTURES "arm64;x86_64")

add_executable(WallpaperVideoExtensionFix MACOSX_BUNDLE main.cpp)

# Link against the necessary macOS frameworks
target_link_libraries(WallpaperVideoExtensionFix
        "-framework CoreFoundation"
        "-framework CoreServices"
        "-framework ApplicationServices"
)


set_target_properties(WallpaperVideoExtensionFix PROPERTIES
        MACOSX_BUNDLE_GUI_IDENTIFIER "com.proton0.WallpaperVideoExtensionFix"
        MACOSX_BUNDLE_BUNDLE_VERSION "1.0.0"
        MACOSX_BUNDLE_SHORT_VERSION_STRING "1.0"
        MACOSX_BUNDLE_COPYRIGHT "Copyright (C) 2024 Proton0"
        MACOSX_BUNDLE_INFO_STRING "A simple patch for WallpaperVideoExtension to allow Custom Screensavers"
)
