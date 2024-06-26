
# Copyright (c) 2016 Juan Delgado (JuDelCo)
# License: MIT License
# MIT License web page: https://opensource.org/licenses/MIT

# ----------------------------------------------------------------------------------------------

cmake_minimum_required(VERSION 3.8)

project(dmentitascpp CXX)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
INCLUDE(cmake/ModuleCompilerDefenses.cmake)

ModuleSetCompileOptions()

LibImport("dmentitascpp" "src")

if (PROJECT_IS_TOP_LEVEL) # need cmake 3.21+
    ExeImport("test" "dmentitascpp")
endif(PROJECT_IS_TOP_LEVEL)
