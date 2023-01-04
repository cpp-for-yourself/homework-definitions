if(NOT TARGET GTest::gtest_main)
  add_subdirectory(${PROJECT_SOURCE_DIR}/external/googletest external/googletest)
  endif()

include(GoogleTest)
set(VALIDATION_TEST validation_tests)
add_executable(${VALIDATION_TEST}
  test_string_split.cpp
  test_string_trim.cpp)
target_link_libraries(${VALIDATION_TEST} GTest::gtest_main string_split string_trim)
gtest_discover_tests(${VALIDATION_TEST} WORKING_DIRECTORY ${PROJECT_DIR})
