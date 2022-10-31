cmake_minimum_required(VERSION 3.0.2)
project(vnoid_world)

find_package(catkin)
catkin_package()

if (EXISTS ${PROJECT_SOURCE_DIR}/vnoid)
  execute_process(COMMAND git pull
    WORKING_DIRECTORY ${PROJECT_SOURCE_DIR}/vnoid)
else ()
  execute_process(COMMAND git clone https://github.com/ytazz/vnoid.git
    WORKING_DIRECTORY ${PROJECT_SOURCE_DIR})
endif()

configure_file(${PROJECT_SOURCE_DIR}/sample/sample_field.cnoid.in ${PROJECT_SOURCE_DIR}/sample/sample_field.cnoid @ONLY)
