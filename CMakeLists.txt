cmake_minimum_required(VERSION 3.14)

project(soft_mesh)

set(ROOT_DIR ${CMAKE_CURRENT_SOURCE_DIR})

add_executable(soft_mesh_mapping ${ROOT_DIR}/soft_mesh_mapping/main.cpp)

