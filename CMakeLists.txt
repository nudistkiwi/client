cmake_minimum_required(VERSION 3.1...3.16)
project(https_server_basic VERSION 1.0)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

if (UNIX)
set(CMAKE_CXX_FLAGS "-Wall -Wextra")
set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")
set(CMAKE_CXX_FLAGS_RELEASE "-lboost_system -lboost_thread -lpthread -pthread")
endif (UNIX)



if (WIN32)
include_directories("C:/Program Files/boost_1_74_0")
target_include_directories(https_server_basic INTERFACE "C:/Program Files/boost_1_74_0")
link_directories("C:/Program Files/boost_1_74_0/lib64-msvc-14.1")
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
endif (WIN32)


include_directories(include)
add_executable(client example/main.cpp)
   


