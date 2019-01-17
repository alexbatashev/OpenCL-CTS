add_khronos_executable(device_timer
    main.c
    test_device_timer.c
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/parseParameters.cpp
    ../../test_common/harness/msvc9.c
)

target_link_libraries(device_timer ${OpenCL_LIBRARIES})

add_test(NAME runDeviceTimerTest
        COMMAND device_timer
        )
