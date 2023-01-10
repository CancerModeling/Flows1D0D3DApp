#////////////////////////////////////////////////////////////////////////////////
#//  Copyright (c) 2020-2021 Prashant K. Jha, Tobias Koeppl, Andreas Wagner
#//
#//  Distributed under the Boost Software License, Version 1.0. (See accompanying
#//  file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#////////////////////////////////////////////////////////////////////////////////

cmake_minimum_required(VERSION 3.12 FATAL_ERROR)

# ****************************************************************************
# Project information
# ****************************************************************************
project(Flows1D0D3DApp LANGUAGES CXX)

set(CMAKE_PROJECT_DESCRIPTION "Collection of tumor growth models")

# version
set(VERSION_MAJOR 0)
set(VERSION_MINOR 1)
set(VERSION_UPDATE 0)

# disable tests apps and python bindings
set(LibMacrocirculation_Enable_Tests OFF CACHE BOOL "Build test executibles and perform tests")
set(LibMacrocirculation_Enable_Apps OFF CACHE BOOL "Includes the apps in our build process")
set(LibMacrocirculation_Enable_Python_Bindings OFF CACHE BOOL "Adds the python bindings to our build process")
add_subdirectory(external/Flows1D0D3D)

add_executable(SimpleLinearizedSolver simple_linearized_solver.cpp)
target_link_libraries(SimpleLinearizedSolver LibMacrocirculation)
