cmake_minimum_required(VERSION 2.8)
project(tile_delivery)

find_library(gflags REQUIRED)
find_library(glog REQUIRED)
find_library(folly REQUIRED)
find_library(pthread REQUIRED)
find_library(proxygenhttpserver REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
        EchoStats.h
        EchoHandler.h
        EchoHandler.cpp
        EchoServer.cpp
        )

add_executable(tile_delivery ${SOURCE_FILES})
target_link_libraries(tile_delivery gflags glog pthread folly proxygenhttpserver)