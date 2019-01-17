add_khronos_executable(device_execution
    device_info.cpp
    device_queue.cpp
    enqueue_block.cpp
    enqueue_flags.cpp
    enqueue_multi_queue.cpp
    enqueue_ndrange.cpp
    enqueue_wg_size.cpp
    execute_block.cpp
    host_multi_queue.cpp
    host_queue_order.cpp
    main.c
    nested_blocks.cpp
    utils.cpp
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(device_execution ${OpenCL_LIBRARIES})

add_test(NAME runDeviceExecutionTest
        COMMAND device_execution all
        )
