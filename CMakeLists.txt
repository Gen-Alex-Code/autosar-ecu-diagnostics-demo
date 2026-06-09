cmake_minimum_required(VERSION 3.20)

project(
    autosar_ecu_diagnostics_demo
    VERSION 0.1.0
    DESCRIPTION "AUTOSAR-inspired ECU diagnostics simulator"
    LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(autosar_ecu_diagnostics_demo
    src/main.cpp
)

target_include_directories(autosar_ecu_diagnostics_demo
    PRIVATE
        ${PROJECT_SOURCE_DIR}/include
)

if(MSVC)
    target_compile_options(autosar_ecu_diagnostics_demo PRIVATE /W4)
else()
    target_compile_options(autosar_ecu_diagnostics_demo PRIVATE -Wall -Wextra -Wpedantic)
endif()