#PROJ ROOT DIR

cmake_minimum_required(VERSION 3.16)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)

if($ENV{BUILD_DEBUG_TYPE})
	set(CMAKE_BUILD_TYPE Debug)
	message("-- BUILD_TYPE: Debug")

	add_compile_definitions(DEBUG_BUILD)
else()
	set(CMAKE_BUILD_TYPE Release)
	message("-- BUILD_TYPE: Release")

	add_compile_definitions(RELEASE_BUILD)
endif()

PROJECT(OpenGLRendering VERSION 0.1)


add_subdirectory(${CMAKE_SOURCE_DIR}/src)
add_subdirectory(${CMAKE_SOURCE_DIR}/assets)

#file(COPY ${CMAKE_BINARY_DIR}/compile_commands.json DESTINATION ${CMAKE_SOURCE_DIR})

