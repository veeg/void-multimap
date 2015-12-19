cmake_minimum_required (VERSION 3.2.0)

project (multimap LANGUAGES C)

add_subdirectory (src)
add_subdirectory (doc)

enable_testing()
add_custom_target (build_and_test ${CMAKE_CTEST_COMMAND} -v)
add_subdirectory (test)



