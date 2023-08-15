if(NOT TARGET GTest::gtest_main)
  add_subdirectory(${PROJECT_SOURCE_DIR}/external/googletest external/googletest)
  endif()

include(GoogleTest)
set(VALIDATION_TEST validation_tests)
add_executable(${VALIDATION_TEST}
  drawer_test.cpp
  image_test.cpp
  stb_image_data_view_test.cpp)
target_link_libraries(${VALIDATION_TEST} drawer stb_image_data_view image GTest::gtest_main)
gtest_discover_tests(${VALIDATION_TEST} WORKING_DIRECTORY ${PROJECT_DIR})
