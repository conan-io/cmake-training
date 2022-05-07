cmake_minimum_required(VERSION 3.9.1)
project(contumerTest)

add_library(greeting greeting/greeting.cpp)
target_include_directories(greeting PUBLIC ${CMAKE_CURRENT_LIST_DIR}/greeting/include)

add_executable(consumer main.cpp)
target_link_libraries(consumer greeting)
