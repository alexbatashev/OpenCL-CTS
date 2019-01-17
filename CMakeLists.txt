set( CONFORMANCE_SUFFIX "" )

project(CLConform${CONFORMANCE_SUFFIX})

cmake_minimum_required(VERSION 3.1)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

add_definitions(-DCL_USE_DEPRECATED_OPENCL_2_1_APIS=1)
add_definitions(-DCL_USE_DEPRECATED_OPENCL_2_0_APIS=1)
add_definitions(-DCL_USE_DEPRECATED_OPENCL_1_2_APIS=1)
add_definitions(-DCL_USE_DEPRECATED_OPENCL_1_1_APIS=1)
add_definitions(-DCL_USE_DEPRECATED_OPENCL_1_0_APIS=1)

find_package(OpenCL REQUIRED)

include_directories(SYSTEM ${OpenCL_INCLUDE_DIRS})
include_directories(${CLConform_SOURCE_DIR}/test_common/harness
        ${CLConform_SOURCE_DIR}/test_common/gles
        ${CLConform_SOURCE_DIR}/test_common/gl
        ${CMAKE_CURRENT_SOURCE_DIR}/test_common/harness)

include(KhronosExecutable)

enable_testing()

add_subdirectory(test_conformance)
