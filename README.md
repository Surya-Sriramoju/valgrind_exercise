# Valgrind Exercise

## Steps to run the code
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```
## Valgrind Test

```bash
- The test was run initially and 2 bugs were found out
- The 2 bugs were.
1- Memory Leak, where the pointer was deleted
2- Unused declared varaible, where the variable was initialised with a value.
- The command used for running the valgrind test is: 
  valgrind --leak-check=full --show-leak-kinds=all ./build/app/shell-app
```

## Extra Credit

- When the valgrind test was run with the static link in CMakeLists.txt in app directory, the valgrind output gave more errors
- Generally, the valgrind tool is powerful and detects the issues both in dynamic and static links. In this case, when such a link is created all the dependent libraries are included in the executable itself and that is causing the issues.

