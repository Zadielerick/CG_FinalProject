cmake_minimum_required(VERSION 3.5)

project(SRV_PC)
set(SRV_PC_VERSION_MAJOR 0)
set(SRV_PC_VERSION_MINOR 1)

set(CMAKE_BUILD_TYPE Debug)

#Searching for source files
file(GLOB APP_SOURCES RELATIVE ${CMAKE_SOURCE_DIR} *.cpp)
file(GLOB COMMON_SOURCES RELATIVE ${CMAKE_SOURCE_DIR} common/*.cpp)

add_executable(srv_pc ${APP_SOURCES} ${COMMON_SOURCES})
#add_executable(camera_calibration camera_calibration.cpp)
find_package(glfw3 REQUIRED)
find_package(GLEW 2.0 REQUIRED)
find_package(OpenCV REQUIRED)
include_directories(${CMAKE_SOURCE_DIR} ${OpenCV_INCLUDE_DIRS})
target_link_libraries(srv_pc glfw GLEW GL ${OpenCV_LIBS})
#target_link_libraries(camera_calibration ${OpenCV_LIBS})
