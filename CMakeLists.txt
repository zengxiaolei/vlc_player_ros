cmake_minimum_required(VERSION 3.0.2)
project(vlc_player_ros)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  actionlib
  actionlib_msgs
  genmsg
  message_generation
)
catkin_python_setup()

add_action_files(FILES
VlcPlayer.action )

generate_messages(DEPENDENCIES
  actionlib_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS
  message_runtime
  std_msgs
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(
    PROGRAMS
      node/vlc_player
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})