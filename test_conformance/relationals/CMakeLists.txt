add_khronos_executable(relationals
    main.c
    test_relationals.cpp
    test_comparisons_float.cpp
    test_comparisons_double.cpp
    test_shuffles.cpp
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/threadTesting.c
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/conversions.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(relationals ${OpenCL_LIBRARIES})

add_test(NAME RelationalsTest
        COMMAND relationals
        )

