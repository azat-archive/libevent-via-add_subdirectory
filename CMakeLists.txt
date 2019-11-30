project(foo)
cmake_minimum_required(VERSION 3.1.2 FATAL_ERROR)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/libs)
message("CMAKE_LIBRARY_OUTPUT_DIRECTORY = ${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
add_subdirectory(libevent EXCLUDE_FROM_ALL)
add_library(lib SHARED lib.c)
target_link_libraries(lib event_core_shared)
message("CMAKE_LIBRARY_OUTPUT_DIRECTORY = ${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
