add_khronos_executable(thread_dimensions
        main.c
    test_thread_dimensions.c
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/threadTesting.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/typeWrappers.cpp
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/conversions.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

if(MSVC)
    target_compile_options(thread_dimensions PUBLIC "/arch:SSE2")
else()
    target_compile_options(thread_dimensions PUBLIC "-msse2")
endif()

target_link_libraries(thread_dimensions ${OpenCL_LIBRARIES})

add_test(NAME ThreadDimensionsTest
        COMMAND thread_dimensions
        )
