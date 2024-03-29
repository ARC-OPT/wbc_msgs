cmake_minimum_required(VERSION 3.8)
project(wbc_msgs)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)

################################################
## Declare ROS messages, services and actions ##
################################################

set(msg_files
  "msg/RigidBodyState.msg"
  "msg/TaskConfig.msg"
  "msg/TaskStatus.msg"
  "msg/RadialPotentialField.msg"
  "msg/RadialPotentialFieldVector.msg"
  "msg/WbcTimingStats.msg"
  "msg/TaskWeights.msg"
  "msg/TaskActivation.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES builtin_interfaces std_msgs geometry_msgs
)
ament_export_dependencies(rosidl_default_runtime)

ament_package()
