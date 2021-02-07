cmake_minimum_required(VERSION 3.17)

project(cmake_testapp)

set(CMAKE_CXX_STANDARD 20)

add_executable(cmake_testapp main.cpp)
add_executable(cmake_testapp_calc main.cpp calc.cpp)
add_library(test_library STATIC calc.cpp)