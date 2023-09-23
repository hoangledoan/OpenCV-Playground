cmake_minimum_required (VERSION 3.0)

Project(gui)

set (CMake_CXX_STANDARD 11)

IF(EXISTS ${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
    conan_basic_setup()
ENDIF()

# Requires OpenCV
FIND_PACKAGE( OpenCV 4.0.0 REQUIRED )
MESSAGE("OpenCV version : ${OpenCV_VERSION}")


ADD_EXECUTABLE(gui main.cpp )
TARGET_LINK_LIBRARIES(gui ${OpenCV_LIBS} ${CONAN_LIBS} ) 
