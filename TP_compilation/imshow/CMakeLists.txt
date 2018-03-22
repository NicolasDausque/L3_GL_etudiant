cmake_minimum_required (VERSION 3.0)
project (imshow)
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra" )

find_package( PkgConfig REQUIRED )

pkg_check_modules( OPENCV REQUIRED opencv )
include_directories( ${OPENCV_INCLUDE_DIRS} )

#find_package( ZLIB REQUIRED )
#include_directories( ${ZLIB_INCLUDE_DIRS} )


add_executable(imshow imshow.cpp)
target_link_libraries(imshow  ${OPENCV_LIBRARIES} )