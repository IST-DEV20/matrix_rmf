cmake_minimum_required(VERSION 2.8.3)
project(clober_gazebo)

find_package(catkin REQUIRED COMPONENTS
  gazebo_ros
  roscpp
  std_msgs
  message_generation
  sensor_msgs
  geometry_msgs
  tf
)

find_package(gazebo REQUIRED)

catkin_package(
 LIBRARIES ${PROJECT_NAME}
 DEPENDS gazebo_ros roscpp std_msgs sensor_msgs geometry_msgs tf
)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${GAZEBO_INCLUDE_DIRS}
)

install(DIRECTORY launch models rviz worlds 
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

