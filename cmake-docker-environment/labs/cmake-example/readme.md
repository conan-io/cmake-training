# cmake-example
These are similar to the make-example exercises. You'll see how a single  CMakeLists.txt file generates a MakeFile file for a variety of system configurations.

## Exercise 1: Generate the MakeFile file and build the executable
   ```
   $ cd cmake-example
   $ mkdir build && cd build
   $ cmake ..
   $ make
   $ ./greeting
   ```

## Exercise 2: Examine the flexibility of CMake's MakeFile file
Make a slight change to greeting.cpp and build again.
   ```
   $ make
   $ ./greeting
   ```
