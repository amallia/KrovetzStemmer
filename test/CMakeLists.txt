file(GLOB TEST_SOURCES *Test.cpp)
foreach(TEST_SRC ${TEST_SOURCES})
  get_filename_component (TEST_SRC_NAME ${TEST_SRC} NAME_WE)
  add_executable(${TEST_SRC_NAME} ${TEST_SRC})
    target_link_libraries(${TEST_SRC_NAME}
    gtest
    gmock
    KrovetzStemmer
    )
  add_test(${TEST_SRC_NAME} ${TEST_SRC_NAME})
endforeach(TEST_SRC)