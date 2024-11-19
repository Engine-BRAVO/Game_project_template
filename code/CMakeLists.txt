cmake_minimum_required(VERSION 3.10)

# Add the Engine-Bravo directory
add_subdirectory(external/Engine-Bravo/code)

# Set the source directory
set(SOURCE_DIR ${CMAKE_SOURCE_DIR}/src)

# Find all source files in the src directory
file(GLOB_RECURSE SOURCES ${SOURCE_DIR}/*.cpp ${SOURCE_DIR}/*.h)

# Add the executable
add_executable(GameProject ${SOURCES})

# Include directories
include_directories(${SOURCE_DIR} ${CMAKE_SOURCE_DIR}/inc)

# Link the Engine-Bravo library
target_link_libraries(GameProject PUBLIC EngineBravo)