add_khronos_executable(allocations
        main.cpp
        allocation_execute.cpp
        allocation_fill.cpp
        allocation_functions.cpp
        allocation_utils.cpp
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/threadTesting.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/testHarness.c
        ../../test_common/harness/typeWrappers.cpp
        ../../test_common/harness/mt19937.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/parseParameters.cpp
        )

target_link_libraries(allocations ${OpenCL_LIBRARIES})

add_test(NAME runAllocationsTest
         COMMAND allocations all
)
