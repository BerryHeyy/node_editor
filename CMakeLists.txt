cmake_minimum_required(VERSION 3.21)

project(node_editor C)

set(LIBRARY_OUTPUT_PATH "${CMAKE_BINARY_DIR}")
set(EXECUTABLE_OUTPUT_PATH "${CMAKE_BINARY_DIR}")

add_subdirectory(deps/lsockengine)

set (NODE_EDITOR_SOURCES
	main.c
)
list(TRANSFORM NODE_EDITOR_SOURCES PREPEND "src/")

add_executable(${PROJECT_NAME} ${NODE_EDITOR_SOURCES})
target_link_libraries(${PROJECT_NAME} lise)
target_include_directories(${PROJECT_NAME} PRIVATE deps/lsockengine/engine/include)
