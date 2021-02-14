# initially empty. We can start filling it up by inserting a live template for Boost with libs.
# Press Ctrl+J or click Code | Insert Live Template, and choose boost_with_libs:
#----------------------------
## see https://cmake.org/cmake/help/latest/module/FindBoost.html
#find_package(Boost REQUIRED COMPONENTS components you would like to link with)
#
#include_directories(${Boost_INCLUDE_DIR})
## Note: a target should be already defined using 'add_executable' or 'add_library'
#target_link_libraries(TargetName ${Boost_LIBRARIES})
#------------------------------ adjust to:

set(Boost_USE_STATIC_LIBS OFF) #enable dynamic linking

# search for unit_test_framework
find_package(Boost REQUIRED COMPONENTS unit_test_framework)

include_directories(${Boost_INCLUDE_DIR})

# create a cmake_testapp_boost target from test.cpp
add_executable(cmake_testapp_boost tests.cpp)

# link Boost libraries to the new target
target_link_libraries(cmake_testapp_boost ${Boost_LIBRARIES})

# link Boost with code library
target_link_libraries(cmake_testapp_boost test_library)