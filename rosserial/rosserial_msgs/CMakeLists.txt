cmake_minimum_required(VERSION 3.7.2)
project(rosserial_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
)

add_message_files(FILES
  Log.msg
  TopicInfo.msg
  Esp_image.msg
)

add_service_files(FILES
  RequestParam.srv
)

generate_messages()

catkin_package(CATKIN_DEPENDS
  message_runtime
)
