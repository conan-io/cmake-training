# make-example
Source code for testing g++ commands and a makefile

## Exercise 1: Generate Object Files
   ```
   cd make-example
   g++ -c main.cpp
   g++ -c greeting.cpp
   ```

## Exercise 2: Link Object Files into an Executable
   ```
   g++ -o greetingTest main.o greeting.o
   ./greetingTest
   ```
   
## Exercise 3: Building from a MakeFile file
Edit the source code so that some, but not all files will recompile. Call make and run the executable.
   ```
   make
   ./greetingTest
   ```