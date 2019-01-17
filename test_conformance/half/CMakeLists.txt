add_khronos_executable(half
        cl_utils.c
        Test_vLoadHalf.c
        Test_roundTrip.c
        Test_vStoreHalf.c main.c
        ../../test_common/harness/msvc9.c
        ../../test_common/harness/mingw_compat.c
        ../../test_common/harness/errorHelpers.c
        ../../test_common/harness/ThreadPool.c
        ../../test_common/harness/parseParameters.cpp
        ../../test_common/harness/kernelHelpers.c
)

target_link_libraries(half ${OpenCL_LIBRARIES})

add_test(NAME runHalfTest
        COMMAND half
        )

