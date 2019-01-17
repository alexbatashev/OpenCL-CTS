add_khronos_executable(non_uniform_work_group
    main.cpp
    test_advanced_2d.cpp
    test_advanced_3d.cpp
    test_advanced_other.cpp
    test_basic.cpp
    TestNonUniformWorkGroup.cpp
    tools.cpp
    ../../test_common/harness/testHarness.c
    ../../test_common/harness/errorHelpers.c
    ../../test_common/harness/kernelHelpers.c
    ../../test_common/harness/msvc9.c
    ../../test_common/harness/parseParameters.cpp
)

target_link_libraries(non_uniform_work_group ${OpenCL_LIBRARIES})

add_test(NAME NonUniformWorkGroupTest
        COMMAND non_uniform_work_group
        )
