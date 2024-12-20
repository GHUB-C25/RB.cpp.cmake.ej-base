cmake_minimum_required(VERSION 3.10)
project(Autograding)

file(GLOB SOURCES "*.cpp")

# Define the default parameters options

option(MAIN_EXECUTABLE "Enable Main Executable" OFF)

option(VISUAL_STUDIO_DEBUG_NORMAL "Enable Visual Studio Debugging" OFF)

# Add executables

if(MAIN_EXECUTABLE)
    add_executable(exercise ${SOURCES})
endif()

if(VISUAL_STUDIO_DEBUG_NORMAL)
    # Add executable target for visual studio debugging
    add_executable(dexercise ${SOURCES})
    set_target_properties(dexercise PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
    target_compile_options(dexercise PRIVATE -g)
endif()
