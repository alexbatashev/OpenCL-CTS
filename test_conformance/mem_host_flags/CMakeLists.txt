add_khronos_executable(mem_host_flags
    main.cpp
    mem_host_buffer.cpp
    mem_host_image.cpp
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/threadTesting.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/genericThread.cpp
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/typeWrappers.cpp
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/conversions.c
    ../../test_common/harness/ThreadPool.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(mem_host_flags ${OpenCL_LIBRARIES})

add_test(NAME MemHostFlagsTest
        COMMAND mem_host_flags
        )
