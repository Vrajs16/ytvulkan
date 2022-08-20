cmake_minimum_required(VERSION 3.23)
project(ytvulkan)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)

execute_process(COMMAND ${CMAKE_SOURCE_DIR}/shaders.sh WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

add_executable(ytvulkan main.cpp
        lve_window.cpp
        first_app.cpp
        lve_pipeline.cpp
        lve_device.cpp
        lve_swap_chain.cpp


        lve_window.hpp
        first_app.hpp
        lve_pipeline.hpp
        lve_device.hpp
        lve_swap_chain.hpp lve_model.cpp lve_model.hpp lve_game_object.cpp lve_game_object.hpp)

target_link_libraries(ytvulkan PRIVATE Vulkan::Vulkan -lglfw)