# ======================================================================
# artdaq_runcontrol_gui main build file
#
#  cd .../path/to/build/directory
#  source .../path/to/artdaq_runcontrol_gui/ups/setup_for_development
#  cmake [-DCMAKE_INSTALL_PREFIX=/install/path]
#        -DCMAKE_BUILD_TYPE=$CETPKG_TYPE
#        $CETPKG_SOURCE
#  make
#  make test
#  make install
#  make package (builds distribution tarfile)
#  buildtool
# ======================================================================



# use cmake 3.7 or later
cmake_minimum_required (VERSION 3.19 FATAL_ERROR)

find_package(cetmodules 3.16.00 REQUIRED)

project(artdaq-runcontrol-gui VERSION 1.04.00)

include(CetCMakeEnv)
cet_cmake_env()

cet_set_compiler_flags(DIAGS VIGILANT
  WERROR
  NO_UNDEFINED
  EXTRA_FLAGS -Wall -Wextra -pedantic -Wconversion
  )

SET ( SANITIZE_ADDRESS $ENV{SANITIZE_ADDRESS} )
IF ( SANITIZE_ADDRESS )
  MESSAGE (STATUS "Enable  -fsanitize=address -Wno-unused-command-line-argument -fno-omit-frame-pointer")
  cet_add_compiler_flags(-fsanitize=address -Wno-unused-command-line-argument -fno-omit-frame-pointer)
ENDIF()

#cet_report_compiler_flags()

# these are minimum required versions, not the actual product versions
#find_ups_product( TRACE v3_09_01 )

set(TOP_CMAKE_BINARY_DIR ${CMAKE_CURRENT_BINARY_DIR})

include(CetTest)

# source
add_subdirectory(artdaq-runcontrol)
# add_subdirectory(test)


cet_cmake_config()