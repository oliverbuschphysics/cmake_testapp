# comments here as in Pycharm
cmake_minimum_required(VERSION 3.17)

project(cmake_testapp)

set(CMAKE_CXX_STANDARD 20)

add_executable(cmake_testapp main.cpp test/tests.cpp test/tests.h)
add_executable(cmake_testapp_calc main.cpp calc.cpp)
add_library(test_library STATIC calc.cpp)

include_directories(includes/math)
include_directories(includes/general)

find_library(TEST_LIBRARY test_library lib)
target_link_libraries(cmake_testapp LINK_PUBLIC ${TEST_LIBRARY})

add_subdirectory(test)