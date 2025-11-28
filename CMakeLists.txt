cmake_minimum_required(VERSION 4.2.0)
set(CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "d0edc3af-4c50-42ea-a356-e2862fe7a444")
set(CMAKE_CXX_MODULE_STD ON)
project(runcpp LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_SCAN_FOR_MODULES ON)

add_executable(${CMAKE_PROJECT_NAME})

target_sources(
        ${CMAKE_PROJECT_NAME}
        PRIVATE
        src/main.cpp
        PRIVATE FILE_SET CXX_MODULES FILES
        src/ext.cppm
)

set_target_properties(${CMAKE_PROJECT_NAME} PROPERTIES
        CXX_MODULE_STD ON
        CXX_SCAN_FOR_MODULES ON
)
