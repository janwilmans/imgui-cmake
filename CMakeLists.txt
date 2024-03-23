cmake_minimum_required(VERSION 3.16.0 FATAL_ERROR)

project(imgui_example)

if (NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
  message("No build type specified, defaulting to Release, use -DCMAKE_BUILD_TYPE=RelWithDebInfo or =Release to build a release)")
endif()

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(imgui)

include(CMakeLists.warnings.cmake)

add_subdirectory(src)

# add_executable(imgui_example
#   imgui/examples/example_glfw_opengl3/main.cpp
# )

# target_link_libraries(imgui_example
#    PRIVATE
#    imgui::demo
#    imgui::imgui
# )

if(${CMAKE_SIZEOF_VOID_P} EQUAL 4)
   set(TARGETBITS 32)
else()
   set(TARGETBITS 64)
endif()

message("")
message("${PROJECT_NAME} configured to run on:  ${CMAKE_SYSTEM_NAME} ${TARGETBITS} bit, ${CMAKE_BUILD_TYPE} Mode")
message("${PROJECT_NAME} will be built in:      ${CMAKE_BINARY_DIR}")
message("${PROJECT_NAME} will be installed in:  ${CMAKE_INSTALL_PREFIX}")
message("\n")

