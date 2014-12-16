cmake_minimum_required(VERSION 2.8.3)
project(gazebo_demo)

find_package(Boost REQUIRED)

include(FindPkgConfig)
if(PKG_CONFIG_FOUND)
  pkg_check_modules(GAZEBO gazebo)
endif()


include_directories(
    ${GAZEBO_INCLUDE_DIRS}
    ${BOOST_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}
    AddObjectRaceDemo.cpp
)
target_link_libraries(${PROJECT_NAME}
    ${GAZEBO_LIBRARIES}
    ${BOOST_LIBRARIES}
)
