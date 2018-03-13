cmake_minimum_required(VERSION 3.5)

set(project_name MyProject)

project($project_name)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Werror -std=c++14")

set(source_dir "${PROJECT_SOURCE_DIR}/src/")
set(include_dir "${PROJECT_SOURCE_DIR}/includes/")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

file(GLOB source_files "${source_dir}/*.cpp")

add_executable($project_name ${source_files})

target_include_directories($project_name PUBLIC ${include_dir})

if (UNIX)
	add_custom_target(catch-test COMMAND bash test)
endif()
