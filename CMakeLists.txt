cmake_minimum_required(VERSION 3.5.0)
project(uSesmicDetector VERSION 0.0.1 LANGUAGES CXX)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_EXTENSIONS OFF)

# Specify the source files
set(SOURCES
    src/main.cpp
    # Add other source files here as needed
)

# Create the executable
add_executable(uSesmicDetector ${SOURCES})

# Optionally, specify the output directory for the built executable
set_target_properties(uSesmicDetector PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
)

# Include directories (if you have headers)
# target_include_directories(uSesmicDetector PRIVATE include)

# Find and link libraries (if needed)
# find_package(SomeLibrary REQUIRED)
# target_link_libraries(uSesmicDetector SomeLibrary)

# Enable debugging symbols
if(CMAKE_BUILD_TYPE MATCHES Debug)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")
endif()

