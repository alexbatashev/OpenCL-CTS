add_khronos_executable(atomics
        main.c
        test_atomics.cpp
        test_indexed_cases.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/threadTesting.c
        ../../test_common/harness/testHarness.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/mt19937.c
        ../../test_common/harness/conversions.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(atomics ${OpenCL_LIBRARIES})

add_test(NAME runAtomicsTest
        COMMAND atomics all
        )

