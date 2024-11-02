set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fexec-charset=GBK")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fexec-charset=GBK")

cmake_minimum_required(VERSION 3.19)

get_filename_component(ProjectId ${CMAKE_CURRENT_SOURCE_DIR} NAME)
string(REPLACE " " "-" ProjectId ${ProjectId})
project(${ProjectId} C)

set(CMAKE_C_STANDARD 99)

file(GLOB files "${CMAKE_CURRENT_SOURCE_DIR}/*.C")
FOREACH(file ${files})
    get_filename_component(name ${file} NAME)
    add_executable(${name} ${file})
endforeach()