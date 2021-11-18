cmake_minimum_required(VERSION 3.1)


project(OpenGLFramework VERSION 1.0)
add_executable(main src/main.cpp)
# set_property(TARGET main PROPERTY CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-g -std=c++11 -Wformat")

# set_property(TARGET main PROPERTY CXX_STANDARD 11)
target_compile_options(main PRIVATE -Wall)

# glfw
add_subdirectory(lib/glfw EXCLUDE_FROM_ALL)
target_link_libraries(main PRIVATE glfw)

# glew
add_definitions(-DGLEW_STATIC)
add_subdirectory(lib/glew-cmake EXCLUDE_FROM_ALL)
target_link_libraries(main PRIVATE libglew_static)

# glm
add_subdirectory(lib/glm EXCLUDE_FROM_ALL)
target_link_libraries(main PRIVATE glm)
