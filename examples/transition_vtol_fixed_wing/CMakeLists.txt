cmake_minimum_required(VERSION 2.8.12)

project(transition_vtol_fixed_wing)

if(NOT MSVC)
    add_definitions("-std=c++11 -Wall -Wextra")
else()
    add_definitions("-std=c++11 -WX -W2")
endif()

find_package(MAVSDK REQUIRED)

add_executable(transition_vtol_fixed_wing
    transition_vtol_fixed_wing.cpp
)

target_link_libraries(transition_vtol_fixed_wing
    MAVSDK::mavsdk_action
    MAVSDK::mavsdk_telemetry
    MAVSDK::mavsdk
)
