# consume-static-library
Commands for generating a STATIC library and consume it from an executable. Before you start, change to the proper directory and make the build directory.
   ```
   $ cd consume-static-library
   $ mkdir build && cd build
   ```

## Exercise 1: Generate and consume a STATIC libary, check its size
   ```
   $ cmake ..
   $ make
   $ ./greeting
   ```

## Exercise 2: Check the size of the executable
   ```
   $ ls -l greeting
   ```

## Exercise 3: Try deleting the library and running the executable
   ```
   $ rm libgreeting.a
   $ ./greeting
   ```