cmake_minimum_required(VERSION 3.9.1)
project(mainTest)

add_executable(main main.cpp)
target_compile_definitions(main PRIVATE GREETING="Hello!")
target_compile_features(main PRIVATE cxx_std_11)
target_compile_options(main PRIVATE -Wall)
