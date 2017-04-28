add_executable(fst_test
  fst_test.cc
  fst_test.h
)
target_link_libraries(fst_test fst)
add_test(NAME fst_test-test COMMAND fst_test)

add_executable(weight_test
  weight_test.cc
  weight-tester.h
)
target_link_libraries(weight_test fst)
add_test(NAME weight_test-test COMMAND weight_test)

add_executable(algo_test_log algo_test.cc algo_test.h rand-fst.h)
target_link_libraries(algo_test_log fst)
target_compile_definitions(algo_test_log
  PRIVATE TEST_LOG=1)
add_test(NAME algo_test_log-test COMMAND algo_test_log)


add_executable(algo_test_tropical algo_test.cc algo_test.h rand-fst.h)
target_link_libraries(algo_test_tropical fst)
target_compile_definitions(algo_test_tropical
  PRIVATE TEST_TROPICAL=1)
add_test(NAME algo_test_tropical-test COMMAND algo_test_tropical)


add_executable(algo_test_minmax algo_test.cc algo_test.h rand-fst.h)
target_link_libraries(algo_test_minmax fst)
target_compile_definitions(algo_test_minmax
  PRIVATE TEST_MINMAX=1)
add_test(NAME algo_test_minmax-test COMMAND algo_test_minmax)


add_executable(algo_test_lexicographic algo_test.cc algo_test.h rand-fst.h)
target_link_libraries(algo_test_lexicographic fst)
target_compile_definitions(algo_test_lexicographic
  PRIVATE TEST_LEXICOGRAPHIC=1)
add_test(NAME algo_test_lexicographic-test COMMAND algo_test_lexicographic)


add_executable(algo_test_power algo_test.cc algo_test.h rand-fst.h)
target_link_libraries(algo_test_power fst)
target_compile_definitions(algo_test_power
  PRIVATE TEST_POWER=1)
add_test(NAME algo_test_power-test COMMAND algo_test_power)

