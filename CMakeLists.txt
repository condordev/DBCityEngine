cmake_minimum_required(VERSION 3.18)

project(DBCityEngine LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)  # no need to call qt5_add_resources

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt5 REQUIRED Core Gui Widgets)
#find_package(Qt5 COMPONENTS Widgets REQUIRED)

set(SOURCES
    main.cpp
    cityengine.cpp
    mainwindow.cpp
    citytablemodel.cpp
    cities.qrc)
set(HEADERS
    cityengine.h
    citytablemodel.h
    mainwindow.h)

#set(RESOURCE
#    ${CMAKE_CURRENT_SOURCE_DIR}/cities.qrc
#)
#qt5_add_resources(RESOURCE_ADDED ${RESOURCE})


add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

target_link_libraries(DBCityEngine Qt${QT_VERSION_MAJOR}::Core Qt${QT_VERSION_MAJOR}::Gui Qt${QT_VERSION_MAJOR}::Widgets)
