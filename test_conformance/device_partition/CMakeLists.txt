add_khronos_executable(device_partition
    main.c
    test_device_partition.cpp
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/threadTesting.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/genericThread.cpp
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/conversions.c
    ../../test_common/harness/typeWrappers.cpp
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(device_partition ${OpenCL_LIBRARIES})

add_test(NAME runDevicePartitionTest
        COMMAND device_partition
        )
