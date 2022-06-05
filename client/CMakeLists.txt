cmake_minimum_required(VERSION 3.16)

project(client)

set(THREADS_PREFER_PTHREAD_FLAG ON)

find_package(Threads REQUIRED)
find_package(Boost COMPONENTS filesystem REQUIRED)

INCLUDE_DIRECTORIES(${Boost_INCLUDE_DIRS})

ADD_EXECUTABLE(client main.cpp)

target_include_directories(client PUBLIC ${CMAKE_SOURCE_DIR}../../include)

target_link_libraries(client Threads::Threads)

target_link_libraries(client ${Boost_FILESYSTEM_LIBRARY})
