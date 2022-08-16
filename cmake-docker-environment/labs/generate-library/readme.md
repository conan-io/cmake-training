# generate-library
Commands for generating a STATIC or SHARED library. Before you start, change to the proper directory and make the build directory.
   ```
   cd generate-library
   mkdir build && cd build
   ```

## Exercise 1: Generate a STATIC libary
Remove add_executable line from CMakeLists.txt. Replace it with add_library.
   ```
   add_library(greeting STATIC greeting.cpp)
   ```
Then, enter this on the command line:
   ```
   cmake ..
   make
   ```

## Exercise 2: Generate a SHARED library
Replace STATIC with SHARED in CMakeLists.txt.
   ```
   add_library(greeting SHARED greeting.cpp)
   ```
Then, enter this on the command line:
   ```
   cmake ..
   make
   ```

## Exercise 3: Have the flexibility to generate either a STATIC or SHARED library
Remove the keyword STATIC or SHARED from the add_library statement in CMakeLists.txt.
   ```
   add_library(greeting greeting.cpp)
   ```
Then you'll have the flexibility to build either library type from the commandline.

For a STATIC library enter:
   ```
   cmake ..
   make
   ```
For a SHARED library enter:
   ```
   cmake -D BUILD_SHARED_LIBS=ON ..
   make
   ```
