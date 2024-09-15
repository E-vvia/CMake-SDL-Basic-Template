project("Engine" VERSION 1.0)

add_library(${PROJECT_NAME} SHARED)

include(GenerateExportHeader)


target_sources(${PROJECT_NAME}
    PRIVATE
        src/engine.cpp
)

target_include_directories(${PROJECT_NAME}
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)
