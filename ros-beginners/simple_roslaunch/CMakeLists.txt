cmake_minimum_required(VERSION 2.8.3)
project(simple_roslaunch)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  ros_custom_msgs
  roscpp
)

catkin_package(
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

#Executable
add_executable(simple_client
  ros/src/simple_client_with_param.cpp
)
add_dependencies(simple_client
  ${catkin_EXPORTED_TARGETS}
)
target_link_libraries(simple_client
  ${catkin_LIBRARIES}
)
