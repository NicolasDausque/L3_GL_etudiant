cmake_minimum_required (VERSION 3.0)
project (SayHello)

set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra" )

#set( CMAKE_BUILD_TYPE Debug )

add_executable(SayHello sayHello.cpp module1.cpp)
