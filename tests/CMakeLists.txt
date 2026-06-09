#------------------------------------------------------------------------------
# Test Target Configuration
#
# M2 — GoogleTest Operational
#
# This target verifies that:
# - GoogleTest integration works
# - CTest integration works
# - Test discovery works
#
# No diagnostic functionality is tested yet.
#------------------------------------------------------------------------------

# Test executable name.
set(TEST_MAIN "autosar_demo_tests")

# Test source files.
set(TEST_SOURCES
    test_placeholder.cpp
)

# Create the test executable.
add_executable(
    ${TEST_MAIN}
    ${TEST_SOURCES}
)

# Link against GoogleTest's main entry point.
target_link_libraries(
    ${TEST_MAIN}
    PRIVATE
        GTest::gtest_main
)

# Enable automatic test discovery.
include(GoogleTest)

# Register all discovered tests with CTest.
gtest_discover_tests(${TEST_MAIN})