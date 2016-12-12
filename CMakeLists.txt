cmake_minimum_required(VERSION 2.8.3)
project(explore)

find_package(catkin REQUIRED COMPONENTS roscpp costmap_2d navfn)

include_directories(include ${catkin_INCLUDE_DIRS})

catkin_package()

add_executable(explore src/explore.cpp src/explore_frontier.cpp src/loop_closure.cpp)
target_link_libraries(explore ${catkin_LIBRARIES})
if(catkin_EXPORTED_TARGETS)
  add_dependencies(explore ${catkin_EXPORTED_TARGETS})
endif()
