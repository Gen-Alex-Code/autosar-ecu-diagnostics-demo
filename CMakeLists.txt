cmake_minimum_required(VERSION 3.20)

project(
    autosar_ecu_diagnostics_demo
    VERSION 0.1.0
    DESCRIPTION "AUTOSAR-inspired ECU diagnostics simulator"
    LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

option(AUTOSAR_DEMO_ENABLE_TESTS "Enable unit tests" ON)

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

# ---------- GoogleTest + CTest ----------

if(AUTOSAR_DEMO_ENABLE_TESTS)
    include(FetchContent)    # Will download GoogleTest.

    # Declare GoogleTest: It points to the official repo and a tagged version.
    FetchContent_Declare(
        googletest
        GIT_REPOSITORY https://github.com/google/googletest.git  # Official GTest repo.
        GIT_TAG v1.14.0                                          # A stable release tag.
    )
    # For Windows: prevent overriding the parent project's compiler/linker settings.
    set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

    # Download and make GTest available as targets (gtest, gtest_main, gmock, …).
    FetchContent_MakeAvailable(googletest)

    enable_testing()         # Activates CTest.

    add_subdirectory(tests)  # Delegates test target creation to tests/CMakeLists.txt

endif()