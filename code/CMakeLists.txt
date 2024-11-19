cmake_minimum_required(VERSION 3.10)

# Define the project name
project(TempProjectName)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add engine bravo library
add_subdirectory(external/Engine-Bravo/code)

# Include directories
# include_directories(${PROJECT_SOURCE_DIR}/inc)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Engine)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Components)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Global)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Input)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/UI)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Save)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Network)
# include_directories(${PROJECT_SOURCE_DIR}/external/Engine-Bravo/code/inc/Audio)

# Specify the output directories
# set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Set the source directory
set(SOURCE_DIR ${CMAKE_SOURCE_DIR}/src)

# Find all source files in the src directory
file(GLOB_RECURSE SOURCES ${SOURCE_DIR}/*.cpp)

# Add the executable target
add_executable(GameExecutable ${SOURCES})

# Add a dependency to ensure the EngineBravo library is built before the GameProject executable
add_dependencies(GameExecutable Engine_BRAVO)

# Link the Engine-Bravo library
target_link_libraries(GameExecutable PRIVATE EngineBravo)