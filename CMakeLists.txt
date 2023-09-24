cmake_minimum_required(VERSION 3.20)

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CUDA_SEPARABLE_COMPILATION ON)

project(algodts-cuda LANGUAGES CXX CUDA)

find_package(CUDAToolkit REQUIRED)

file(GLOB SOURCES "./*.cpp" "./src/*.cu")

add_executable(algodts ${SOURCES})

target_include_directories(algodts PRIVATE ./include)

target_link_libraries(algodts PRIVATE CUDA::cudart)
