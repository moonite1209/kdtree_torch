cmake_minimum_required(VERSION 3.22)
project(kdtree_torch LANGUAGES CXX CUDA)
set(CMAKE_CXX_STANDARD 20)

find_package(CUDAToolkit REQUIRED)

set(SRC_FILES
"src/test.cu"
)

add_executable(kdtree_torch ${SRC_FILES})
target_link_directories(kdtree_torch PRIVATE /home/moonite/miniconda3/envs/project/lib/python3.12/site-packages/torch/lib)
target_include_directories(kdtree_torch PRIVATE /home/moonite/miniconda3/envs/project/lib/python3.12/site-packages/torch/include
                            /home/moonite/miniconda3/envs/project/lib/python3.12/site-packages/torch/include/torch/csrc/api/include
                            /home/moonite/miniconda3/envs/project/lib/python3.12/site-packages/torch/include/TH
                            /home/moonite/miniconda3/envs/project/lib/python3.12/site-packages/torch/include/THC)
target_link_libraries(kdtree_torch PRIVATE CUDA::cudart)
target_include_directories(kdtree_torch PRIVATE "src/include")