cmake_minimum_required(VERSION 3.17)

set(OMPI_LIB_DIR ${PROJECT_SOURCE_DIR}/ompi/install/lib)
set(OMPI_INCLUDE_DIR ${PROJECT_SOURCE_DIR}/ompi/install/include)

project(ompi-testbench)

add_executable(mpi_hello mpi_hello.c)
target_include_directories(mpi_hello PRIVATE ${OMPI_INCLUDE_DIR})
target_link_libraries(mpi_hello PRIVATE 
    ${OMPI_LIB_DIR}/libmpi.so
    ${OMPI_LIB_DIR}/libopen-pal.so
    ${OMPI_LIB_DIR}/libprrte.so
)