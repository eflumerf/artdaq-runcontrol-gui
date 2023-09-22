file(MAKE_DIRECTORY "${CMAKE_BINARY_DIR}/resources")
set(GUI_RESOURCES_DIRECTORY "${CMAKE_BINARY_DIR}/resources")

install(DIRECTORY "${CMAKE_BINARY_DIR}/resources" DESTINATION ./${artdaq-runcontrol-gui_EXEC_PREFIX} FILE_PERMISSIONS USE_SOURCE_PERMISSIONS)

add_subdirectory(images)

