add_khronos_executable(vec_step
    globals.c
        test_step.c
        main.c
        structs.c
        type_replacer.c
        ../../test_common/harness/testHarness.c
        ../../test_common/harness/mt19937.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/parseParameters.cpp
)

if(MSVC)
    target_compile_options(thread_dimensions PUBLIC "/arch:SSE2")
else()
    target_compile_options(thread_dimensions PUBLIC "-msse2")
endif()

target_link_libraries(vec_step ${OpenCL_LIBRARIES})

add_test(NAME VecStepTest
        COMMAND vec_step
        )
