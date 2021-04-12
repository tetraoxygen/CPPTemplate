cmake_minimum_required(VERSION 3.16)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(main)

add_executable(main src/main.cpp)

set_property(TARGET main PROPERTY CXX_STANDARD 14)

install(TARGETS main)

IF (WIN32 AND CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
	target_link_libraries(main -static)
ENDIF()

if (MSVC)
	add_compile_options(/std:c++latest)
endif()