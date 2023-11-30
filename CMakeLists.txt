# Version settings
cmake_minimum_required(VERSION 3.7...3.20)

if (${CMAKE_VERSION} VERSION_LESS 3.12)
	cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

# Project settings
project(
	projeto-oop VERSION 1.0
	DESCRIPTION "Implementação projeto OOP"
	LANGUAGES C CXX
)

# Source Dir variable
set(SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}/src")

# Translations units of the project
set(
	TRANSLATION_FILES
	"${SRC_DIR}/main.cpp"
	"${SRC_DIR}/battlearena.cpp"
	"${SRC_DIR}/pokedex.cpp"
	"${SRC_DIR}/pokemon.cpp"
	"${SRC_DIR}/pokemontrainer.cpp"
)

# Header files of the project
set(
	HEADERS_FILES
	"${SRC_DIR}/battlearena.h"
	"${SRC_DIR}/pokedex.h"
	"${SRC_DIR}/pokemon.h"
	"${SRC_DIR}/pokemontrainer.h"
)

# Executable settings
add_executable(${PROJECT_NAME} ${TRANSLATION_FILES} ${HEADERS_FILES})
target_include_directories(${PROJECT_NAME} PRIVATE "${SRC_DIR}")
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)
