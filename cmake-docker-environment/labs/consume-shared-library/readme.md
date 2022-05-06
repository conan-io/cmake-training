# consume-shared-library
Commands for generating a SHARED library and consume it from an executable. Before you start, change to the proper directory and make the build directory.
   ```
   $ cd consume-shared-library
   $ mkdir build && cd build
   ```
   
## Exercise 1: Generate and consume a STATIC libary, check its size
   ```
   $ cmake -D BUILD_SHARED_LIBS=true ..
   $ make
   $ ./greeting
   ```

## Exercise 2: Check the size of the executable
   ```
   $ ls -l greeting
   ```

## Exercise 3: Try deleting the library and running the executable
   ```
   $ rm libgreeting.so
   $ ./greeting
   ```

## Exercise 4: Change the greeting, rebuild the library, and run the old executable
**greeting.cpp**
   ```
   #include "greeting.h"
   #include <iostream>

   void sayHello() {
	   std::cout << "Hola World!\n";
   }
   ```

**CMakeLists.txt**
   ```
   cmake_minimum_required(VERSION 3.9.1)
   project(contumerTest)

   add_library(greeting greeting/greeting.cpp)
   target_include_directories(greeting PUBLIC ${CMAKE_CURRENT_LIST_DIR}/greeting/include)
   ```

**Command Line**
   ```
   cmake -D BUILD_SHARED_LIBS=true ..
   make
   ./consumer
   ```