project("Game" VERSION 1.0)

add_executable (${PROJECT_NAME} "main.cpp" )

target_link_libraries(${PROJECT_NAME} Engine)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)
endif()


if(WIN32)
      set_target_properties(SDL3-shared PROPERTIES
                      RUNTIME_OUTPUT_DIRECTORY_DEBUG $<TARGET_FILE_DIR:${PROJECT_NAME}>
                      RUNTIME_OUTPUT_DIRECTORY_RELEASE $<TARGET_FILE_DIR:${PROJECT_NAME}>
      )

      set_target_properties(ZEngine PROPERTIES
                      RUNTIME_OUTPUT_DIRECTORY_DEBUG $<TARGET_FILE_DIR:${PROJECT_NAME}>
                      RUNTIME_OUTPUT_DIRECTORY_RELEASE $<TARGET_FILE_DIR:${PROJECT_NAME}>
      )
endif()
