cmake_minimum_required(VERSION 3.9.1)
project(songTest)

add_subdirectory(firstDay)
add_subdirectory(secondDay)

add_library(thirdDay thirdDay/thirdDay.cpp)
target_include_directories(thirdDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/thirdDay/include)
target_link_libraries(thirdDay PUBLIC secondDay)

add_executable(song main.cpp)
target_link_libraries(song thirdDay)
