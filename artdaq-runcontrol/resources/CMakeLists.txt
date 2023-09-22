file(MAKE_DIRECTORY "${CMAKE_BINARY_DIR}/${artdaq-runcontrol-gui_EXEC_PREFIX}/resources")
set(GUI_RESOURCES_DIRECTORY "${CMAKE_BINARY_DIR}/${artdaq-runcontrol-gui_EXEC_PREFIX}/resources")

install(DIRECTORY "${CMAKE_BINARY_DIR}/${artdaq-runcontrol-gui_EXEC_PREFIX}/resources" DESTINATION ./${artdaq-runcontrol-gui_EXEC_PREFIX} FILE_PERMISSIONS USE_SOURCE_PERMISSIONS)

add_subdirectory(images)

