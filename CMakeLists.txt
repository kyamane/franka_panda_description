cmake_minimum_required(VERSION 3.5)

project(franka_panda_description)

include(GNUInstallDirs)

find_package(ament_cmake REQUIRED)

foreach(dir meshes robots)
  install(DIRECTORY ${dir}/
    DESTINATION share/${PROJECT_NAME}/${dir})
endforeach(dir)

# udims::Chain::load() needs the meshes here
install(DIRECTORY meshes
  DESTINATION share
)

ament_environment_hooks(${CMAKE_CURRENT_SOURCE_DIR}/env_hooks/franka_panda_description_env.sh.in)

ament_package()
