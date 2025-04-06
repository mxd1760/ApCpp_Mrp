cmake_minimum_required(VERSION 3.29.0)
project(
  ApCpp_Mrp 
  VERSION 0.0.1
)
add_executable("${PROJECT_NAME}" hello_world.cpp)
add_subdirectory(APCpp APCpp)
target_include_directories("${PROJECT_NAME}" PRIVATE APCpp)
target_link_libraries("${PROJECT_NAME}" APCpp)