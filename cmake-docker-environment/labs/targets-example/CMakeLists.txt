cmake_minimum_required(VERSION 3.9.1)
project(songTest)

add_library(firstDay firstDay/firstDay.cpp)
target_include_directories(firstDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/firstDay/include)

add_library(secondDay secondDay/secondDay.cpp)
target_include_directories(secondDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/secondDay/include)
target_link_libraries(secondDay PUBLIC firstDay)

# thirdDay target

add_executable(song main.cpp)
target_link_libraries(song secondDay)
