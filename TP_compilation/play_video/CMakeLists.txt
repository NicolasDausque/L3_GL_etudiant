cmake_minimum_required (VERSION 3.0)
project (play_video_gui)
set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra" )

find_package( PkgConfig REQUIRED )
pkg_check_modules( PKG REQUIRED gtkmm-3.0 libvlc )
include_directories( ${PKG_INCLUDE_DIRS} )

find_package( Boost REQUIRED COMPONENTS system filesystem )
include_directories( ${Boost_INCLUDE_DIRS} )

include_directories( src )
add_library(play_video STATIC src/play_video/Filesystem.cpp)#notre biblio


add_executable(play_video_gui
  src/play_video_gui/play_video_gui.cpp
  src/play_video_gui/Player_Window.cpp )
target_link_libraries(play_video_gui ${PKG_LIBRARIES} ${Boost_LIBRARIES} play_video)
