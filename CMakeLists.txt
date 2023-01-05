cmake_minimum_required(VERSION 3.0.2)
project(wbc_msgs)

add_compile_options(-std=c++11)
find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  message_generation
)

include(FindPkgConfig)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(
   DIRECTORY msg
   FILES
   RigidBodyState.msg
   TaskConfig.msg
   TaskStatus.msg
   RadialPotentialField.msg
   RadialPotentialFieldVector.msg
)

## Generate added messages and services with any dependencies listed here
generate_messages(
   DEPENDENCIES
   geometry_msgs
)

catkin_package(
  CATKIN_DEPENDS geometry_msgs
)
