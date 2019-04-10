cmake_minimum_required(VERSION 3.5)
project(ur_msgs)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)

## Generate messages in the 'msg' folder
rosidl_generate_interfaces(ur_msgs
   "msg/Analog.msg"
   "msg/Digital.msg"
   "msg/IOStates.msg"
   "msg/RobotStateRTMsg.msg"
   "msg/MasterboardDataMsg.msg"
   "msg/ToolDataMsg.msg"
   "srv/SetPayload.srv"
   "srv/SetIO.srv"
   DEPENDENCIES builtin_interfaces
)

ament_package()
