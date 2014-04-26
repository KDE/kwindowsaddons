project(KWindowsAddons)

cmake_minimum_required(VERSION 2.8.12 FATAL_ERROR)
set(QT_MIN_VERSION "5.2.0")

find_package(ECM 0.0.11 REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR})

include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings)
include(ECMInstallIcons)
include(ECMMarkAsTest)
include(ECMMarkNonGuiExecutable)
include(FeatureSummary)
include(CheckIncludeFiles)

find_package(Qt5 ${QT_MIN_VERSION} CONFIG REQUIRED COMPONENTS
    Test
)

find_package(KF5 REQUIRED COMPONENTS
    KCMUtils
    KDE4Support
)

add_subdirectory( kwinshutdown )
add_subdirectory( kwinstartmenu ) 
add_subdirectory( config )
add_subdirectory( contextmenu)

feature_summary(WHAT ALL   FATAL_ON_MISSING_REQUIRED_PACKAGES)
