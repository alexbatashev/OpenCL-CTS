add_khronos_executable(printf
         test_printf.c
         util_printf.c
         ../../test_common/harness/errorHelpers.c
         ../../test_common/harness/threadTesting.c
         ../../test_common/harness/kernelHelpers.c
         ../../test_common/harness/typeWrappers.cpp
         ../../test_common/harness/conversions.c
         ../../test_common/harness/mt19937.c
         ../../test_common/harness/msvc9.c
         #../../test_common/harness/imageHelpers.cpp
         ../../test_common/harness/parseParameters.cpp
         ../../test_common/harness/kernelHelpers.c
         )

target_link_libraries(printf ${OpenCL_LIBRARIES})

add_test(NAME PrintfTest
        COMMAND printf
        )
