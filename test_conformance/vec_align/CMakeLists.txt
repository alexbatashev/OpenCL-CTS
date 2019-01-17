add_khronos_executable(vec_align
    globals.c
        main.c
        structs.c
        test_vec_align.c
        type_replacer.c
        ../../test_common/harness/testHarness.c
        ../../test_common/harness/mt19937.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/kernelHelpers.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/conversions.c
        ../../test_common/harness/parseParameters.cpp
)

set_source_files_properties(
        COMPILE_FLAGS -msse2)

if(MSVC)
    target_compile_options(vec_align PUBLIC "/arch:SSE2")
else()
    target_compile_options(vec_align PUBLIC "-msse2")
endif()

target_link_libraries(vec_align ${OpenCL_LIBRARIES})

add_test(NAME VecAlignTest
        COMMAND vec_align
        )

