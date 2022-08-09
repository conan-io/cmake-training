# targets-example
This project asks you to create targets that have varying visibility of each other. Before you start, change to the proper directory and make the build directory.
   ```
   cd targets-example
   mkdir build && cd build
   ```
   
## Exercise 1: Create a song executable that uses the thirdDay

**main.cpp**

Remove the comments so that the thirdDay header is included and the thirdDay function is called.
   ```
#include "firstDay.h"
#include "secondDay.h"
#include "thirdDay.h"  //Exercise 1, comment back in

int main() {
	firstDay();
	secondDay();
	thirdDay()   //Exercise 1, comment back in 
	return 0;
}
   ```

**CMakeLists.txt**

Modify CMakeLists.txt so that the executable utilizes thirdDay functionality. Reverse-engineer what you need for the thirdDay target and make any other tweaks.
   ```
   cmake_minimum_required(VERSION 3.9.1)
   project(songTest)

   add_library(firstDay firstDay/firstDay.cpp)
   target_include_directories(firstDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/firstDay/include)

   add_library(secondDay secondDay/secondDay.cpp)
   target_include_directories(secondDay PUBLIC ${CMAKE_CURRENT_LIST_DIR}/secondDay/include)
   target_link_libraries(secondDay PUBLIC firstDay)

   #setup the thirdDay target

   add_executable(song main.cpp)
   target_link_libraries(song secondDay)
   ```

**Command Line**

Run the executable.
   ```
   cmake ..
   make
   ./song
   ```

## Exercise 2: Change the target_include_directory for the thirdDay target to have PRIVATE and INTERFACE visibility

**CMakeLists.txt**

   ```
   ...
   target_include_directories(thirdDay PRIVATE ${CMAKE_CURRENT_LIST_DIR}/thirdDay/include)
   ...
   ```
   ```
   ...
   target_include_directories(thirdDay INTERFACE ${CMAKE_CURRENT_LIST_DIR}/thirdDay/include)
   ...
   ```

**Command Line**

Try compiling and running.
   ```
   cmake ..
   make
   ./song
   ```

## Exercise 3: Create a dependency graph and convert it to a PNG
   ```
   cmake .. --graphviz=song.dot
   dot -Tpng -o song.png song.dot
   ```
