add_khronos_executable(select
        test_select.c
        util_select.c
        ../../test_common/harness/testHarness.c
        ../../test_common/harness/mt19937.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(select ${OpenCL_LIBRARIES})

add_test(NAME SelectTest
        COMMAND select
        )
