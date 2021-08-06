cmake_minimum_required(VERSION 3.5)

project(franka_panda_description)

find_package(ament_cmake REQUIRED)

foreach(dir meshes robots ros2_control)
   install(DIRECTORY ${dir}/
      DESTINATION share/${PROJECT_NAME}/${dir})
endforeach(dir)

ament_package()
