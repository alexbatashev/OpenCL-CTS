add_khronos_executable(generic_address_space
    advanced_tests.cpp
    basic_tests.cpp
    main.cpp
    stress_tests.cpp
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/mt19937.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(generic_address_space ${OpenCL_LIBRARIES})

add_test(NAME GenericAddressSpaceTest
        COMMAND generic_address_space
        )

