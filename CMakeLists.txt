cmake_minimum_required(VERSION 3.10)

# Define the project name
project(TempProjectName)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the source directory
add_subdirectory(code)

# Specify the output directories
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Add the executable target
add_executable(GameExecutable ${CMAKE_SOURCE_DIR}/code/main.cpp)