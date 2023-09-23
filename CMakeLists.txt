cmake_minimum_required (VERSION 3.0)

Project(i/o_images)

set (CMake_CXX_STANDARD 11)

IF(EXISTS ${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup()
ENDIF()

# Requires OpenCV
FIND_PACKAGE( OpenCV 4.0.0 REQUIRED )
MESSAGE("OpenCV version : ${OpenCV_VERSION}")


ADD_EXECUTABLE( sample1 sample1.cpp )
TARGET_LINK_LIBRARIES( sample1 ${OpenCV_LIBS} ${CONAN_LIBS} ) 
