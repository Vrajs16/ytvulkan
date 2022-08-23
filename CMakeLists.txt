cmake_minimum_required(VERSION 3.23)
project(ytvulkan)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)

execute_process(COMMAND ${CMAKE_SOURCE_DIR}/shaders.sh WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})

add_executable(ytvulkan
        
        main.cpp
        first_app.cpp first_app.hpp
        lve_window.cpp lve_window.hpp
        lve_pipeline.cpp lve_pipeline.hpp
        lve_device.cpp lve_device.hpp
        lve_swap_chain.cpp lve_swap_chain.hpp
        lve_model.cpp lve_model.hpp
        lve_game_object.hpp
        lve_renderer.cpp lve_renderer.hpp
        simple_render_system.cpp simple_render_system.hpp

        )

target_link_libraries(ytvulkan PRIVATE Vulkan::Vulkan -lglfw)