cmake_minimum_required(VERSION 2.8.3)
project(autonomous_exploration)


## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  sensor_msgs
  nav_msgs
  geometry_msgs
  move_base_msgs
)

catkin_package()

## Specify additional locations of header files
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  src/obstacle_avoidance.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
