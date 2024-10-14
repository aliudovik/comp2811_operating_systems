cmake_minimum_required(VERSION 3.16)

PROJECT(quaketool VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CLASSES quake.cpp dataset.cpp
        test_quake.cpp)

add_executable(quaketool main.cpp ${CLASSES}
        test_quake.cpp)
add_executable(test_dataset test_dataset.cpp ${CLASSES}
        test_quake.cpp)
add_executable(test_quake test_quake.cpp quake.cpp
        test_quake.cpp)

target_link_libraries(quaketool pthread)
target_link_libraries(test_dataset pthread)
