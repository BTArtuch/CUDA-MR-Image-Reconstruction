cmake_minimum_required(VERSION 3.18)
project(cuda_mri_recon LANGUAGES CXX CUDA)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CUDA_STANDARD 17)
set(CMAKE_CUDA_STANDARD_REQUIRED ON)
set(CMAKE_CUDA_ARCHITECTURES 50)

find_package(CUDAToolkit REQUIRED)

include_directories(include)

add_library(test 
  STATIC
    include/test.hpp
    src/test.cpp
  )

add_executable(hello src/main.cpp)

target_link_libraries(hello test)