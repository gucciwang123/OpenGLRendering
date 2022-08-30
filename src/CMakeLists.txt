add_executable(graph "")
include(${CMAKE_CURRENT_SOURCE_DIR}/sources.cmake)

target_precompile_headers(graph PRIVATE headers/pch.h)

target_include_directories(graph PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/headers)

if(WIN32)
else()
	find_library(LIB_GLEW NAMES libGLEW glew GLEW REQUIRED)
	find_library(LIB_SDL2 NAMES libsdl2 SDL2 REQUIRED)

	target_link_libraries(graph PRIVATE ${LIB_SDL2} PRIVATE ${LIB_GLEW})
endif()


