add_khronos_executable(computeinfo
        main.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/parseParameters.cpp
        ../../test_common/harness/testHarness.c
)

target_link_libraries(computeinfo ${OpenCL_LIBRARIES})

add_test(NAME runComputeinfoTest
        COMMAND computeinfo
        )
