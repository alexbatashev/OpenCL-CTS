add_khronos_executable(c11_atomics
    common.cpp
    host_atomics.cpp
    main.cpp
    test_atomics.cpp
    ../../test_common/harness/ThreadPool.c
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(c11_atomics ${OpenCL_LIBRARIES})

add_test(NAME C11AtomicsTest
        COMMAND c11_atomics
        )
