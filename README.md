# boilerplate4cpp
A boilerplate for C++ projects using minimal CMake and includes CATCH2 for testing.

*Note: This was created and tested only on a single Linux installation, and the testing script is a ShellScript so it definitely won't run on Windows*

*Note: This is the setup which best suited my needs, it might not be the best option for your particular case*

## Using the boilerplate
1. Download the repository
2. Change the project name in CMakeLists.txt and run '*cmake .*'
3. Add whatever header files you want to use (like [Boost](http://www.boost.org) for example) to *includes/* directory
4. Add your source files to *src/* directory
5. Add your test files to *src/tests/* directory (refer to [CATCH2 documentation](https://github.com/catchorg/Catch2) for details on how to write tests)
6. Add the names of your test files you want to include in testing and their corresponding source files to *test* file

In order to build your project run '*make*', and to compile and run the tests run '*make catch-test*'

Note that the testing script pre-compiles catch first to speed up the process of building your test files so there's no need to do that yourself.
