# subdirectory-example
This project asks you to manage targets that are created in several CMakeLists.txt files across subdirectories. Before you start, change to the proper directory and make the build directory.
   ```
   cd subdirectory-example
   mkdir build && cd build
   ```
   
## Exercise 1: Move the thirdDay target functionality into thirdDay/CMakeLists.txt

Reverse engineer what you need from other files.

**CMakeLists.txt**

   ```
   cmake_minimum_required(VERSION 3.9.1)
   project(songTest)

   add_subdirectory(firstDay)
   add_subdirectory(secondDay)

   add_library(thirdDay thirdDay/thirdDay.cpp)
   target_include_directories(thirdDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/thirdDay/include)
   target_link_libraries(thirdDay PUBLIC secondDay)

   add_executable(song main.cpp)
   target_link_libraries(song thirdDay)
   ```

**secondDay/CMakeLists.txt**

   ```
   add_library(secondDay secondDay.cpp)
   target_include_directories(secondDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)
   target_link_libraries(secondDay PUBLIC firstDay)
   ```

**thirdDay/CMakeLists.txt**

   ```
   //Exercise 1
   ```

**Command Line**

Compile and run the executable.
   ```
   cmake ..
   make
   ./song
   ```
