# Root CMakeLists.txt for template C++ project
# Author: Jesper Glas

cmake_minimum_required(VERSION 3.16)

project(
    "cpp-template"
    VERSION 1.0
)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/bin)

set(SOURCE ${PROJECT_SOURCE_DIR}/src)
set(INCLUDE ${PROJECT_SOURCE_DIR}/include)

configure_file(
    ${INCLUDE}/ProjectConfig.hpp.in
    ProjectConfig.hpp
)

add_executable(
    ${PROJECT_NAME}
    ${SOURCE}/main.cpp
)

target_include_directories(
    ${PROJECT_NAME}
    PUBLIC
        ${PROJECT_BINARY_DIR}
        ${INCLUDE}
)