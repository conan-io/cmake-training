cmake_minimum_required(VERSION 3.9.1)
project(songTest VERSION 1.0.0)

add_library(firstDay firstDay.cpp)
target_include_directories(firstDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
