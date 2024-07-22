enable_testing()

include(GoogleTest)
find_package(GTest REQUIRED)

add_executable(testFCIdump testFCIdump.cpp)
target_link_libraries(testFCIdump PUBLIC FCIdump GTest::gmock_main)
target_compile_options(testFCIdump PUBLIC -fpermissive)
gtest_discover_tests(testFCIdump)

#add_test(NAME testFCIdump COMMAND testFCIdump)
