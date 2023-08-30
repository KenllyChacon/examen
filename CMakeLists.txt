cmake_minimum_required(VERSION 3.26)
project(uno)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fopenmp") #Esto solo en OpenMP

include(cmake/CPM.cmake)

CPMAddPackage("gh:fmtlib/fmt#10.0.0")
CPMAddPackage("gh:google/googletest#v1.13.0")#Esto solo en OpenMP
CPMAddPackage("gh:google/benchmark#v1.8.0")#Esto solo en OpenMP

#find_package(MPI REQUIRED)#Esto solo en MPI
#message(STATUS "run: ${MPIEXEC}")#Esto solo en MPI

add_executable(uno main.cpp)
target_link_libraries(uno fmt::fmt benchmark::benchmark) #Esto solo en OpenMP
#target_link_libraries(uno fmt::fmt MPI::MPI_CXX) #Esto solo en MPI