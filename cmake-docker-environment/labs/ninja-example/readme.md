# ninja-example
The project for this lesson contains the same code as cmake-example. However, instead of creating an executable with Make, this lesson will do the same work using the Ninja generator.

## Exercise 1: Examine the generators found in the lab environment
   ```
   cmake --help
   ```

## Exercise 2: Create an executable using Ninja as the generator. Examine the resulting build.ninja file.
Make a slight change to greeting.cpp and build again.
   ```
   cd ninja-example
   mkdir build && cd build
   cmake .. -G Ninja
   cmake --build .
   ./greeting
   ```
