
# Copyright (c) 2016 Juan Delgado (JuDelCo)
# License: MIT License
# MIT License web page: https://opensource.org/licenses/MIT

# ----------------------------------------------------------------------------------------------

cmake_minimum_required(VERSION 3.8)

project(EntitasPP CXX)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
INCLUDE(cmake/ModuleCompilerDefenses.cmake)

ModuleSetCompileOptions()

set(EXECUTABLE_NAME main)
file(GLOB_RECURSE ENTITAS_SRC EntitasPP/*.*pp)

add_executable(${EXECUTABLE_NAME}
	main.cpp
	${ENTITAS_SRC}
)

# -------------------------------------------------------------------------------------------------

set(CONFIGURED_ONCE TRUE CACHE INTERNAL "Flag - CMake has configured at least once")
