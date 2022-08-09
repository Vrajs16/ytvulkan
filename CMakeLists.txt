cmake_minimum_required(VERSION 3.23)
project(ytvulkan)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/shaders DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(ytvulkan main.cpp lve_window.hpp lve_window.cpp first_app.hpp first_app.cpp lve_pipeline.hpp lve_pipeline.cpp )

target_link_libraries(ytvulkan PRIVATE Vulkan::Vulkan -lglfw)