cmake_minimum_required(VERSION 2.8.3)
project(buildit_marker_server)

find_package(catkin REQUIRED COMPONENTS buildit_msgs visualization_marker_tutorials moveit_ros_visualization buildit_ui roscpp visualization_msgs)

include_directories(include ${catkin_INCLUDE_DIRS})

catkin_package(

)

## Declare a cpp executable
# add_executable(buildit_marker_server_node src/buildit_marker_server_node.cpp)
add_executable(buildit_marker_server src/buildit_marker_server.cpp)
target_link_libraries(buildit_marker_server ${catkin_LIBRARIES} yaml-cpp ${QT_LIBRARIES})
add_dependencies(buildit_marker_server buildit_msgs_generate_messages_cpp buildit_msgs_gencpp ${catkin_EXPORTED_TARGETS} ${buildit_ui_EXPORTED_TARGETS} buildit_ui_gencpp) 

install(TARGETS buildit_marker_server 
ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

