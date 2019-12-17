cmake_minimum_required(VERSION 2.8.3)
project(path_test)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)

catkin_package(
)

find_package(CUDA)

include_directories(
  # ${CUDA_INCLUDE_DIRS}
  ${catkin_INCLUDE_DIRS}
)

add_executable(path_test
      src/main.cpp)

add_dependencies(path_test
        ${catkin_EXPORTED_TARGETS}
        )

target_link_libraries(path_test
  ${catkin_LIBRARIES}
)

# cuda_add_library(test_path_cuda
#         src/sample.cu
#         )
