cmake_minimum_required(VERSION 2.8.3)
project(riptide_hardware)
add_compile_options(-std=c++11)

# NOTE: Most dependencies can be taken care of with $(catkin_EXPORTED_TARGETS).
# There is no need to add mention the specific dependency, such as
# <package_name>_gencpp, or <package_name>_gencfg

find_package(catkin REQUIRED
    COMPONENTS
    roslint
    roscpp
    riptide_msgs
    geometry_msgs
    message_filters
    message_generation
    sensor_msgs
    dynamic_reconfigure
)

find_package(Eigen3 REQUIRED)

generate_dynamic_reconfigure_options(
  cfg/Torpedo.cfg
)

catkin_package(
  CATKIN_DEPENDS
    dynamic_reconfigure
)
include_directories(${catkin_INCLUDE_DIRS})



