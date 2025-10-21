# root CMakeLists.txt
cmake_minimum_required (VERSION 3.15)
cmake_policy(SET CMP0091 NEW)

project ("template-cmake")

option(BUILD_TESTS "Build test" ON)

# global configurations
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

set(CMAKE_THREAD_PREFER_PTHREAD TRUE)
set(THREADS_PREFER_PTHREAD_FLAG TRUE)
find_package(Threads REQUIRED)

# add application
add_subdirectory("app")

# add test
if(BUILD_TESTS)
	add_subdirectory("test")
endif()
