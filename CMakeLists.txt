cmake_minimum_required(VERSION 3.5.0)
project(uSeismicDetector VERSION 0.0.1 LANGUAGES CXX)

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
add_executable(uSeismicDetector ${SOURCES})

# Optionally, specify the output directory for the built executable
set_target_properties(uSeismicDetector PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin
)

# Include directories (add the directory where libmseed.h is located)
target_include_directories(uSeismicDetector PRIVATE ${PROJECT_SOURCE_DIR}/lib)

# Enable debugging symbols in Debug mode
if(CMAKE_BUILD_TYPE MATCHES Debug)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")
endif()
