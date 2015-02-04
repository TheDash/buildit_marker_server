cmake_minimum_required(VERSION 2.8.3)
project(buildit_marker_server)

find_package(catkin REQUIRED COMPONENTS buildit_msgs visualization_msgs buildit_ros)

catkin_package(
)

## Declare a cpp executable
# add_executable(buildit_marker_server_node src/buildit_marker_server_node.cpp)
add_executable(buildit_marker_server src/buildit_marker_server.cpp)
target_link_libraries(buildit_marker_server ${catkin_LIBRARIES} yaml-cpp)
add_dependencies(buildit_marker_server buildit_msgs_generate_messages_cpp) 

install(TARGETS buildit_marker_server 
ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

