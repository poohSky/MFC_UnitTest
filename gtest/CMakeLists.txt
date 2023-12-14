cmake_minimum_required(VERSION 3.23)

project(MFC_UnitTest)

SET(CMAKE_CXX_FLAGS "-g -O0 -fprofile-arcs -ftest-coverage -fprofile-instr-generate -fcoverage-mapping")
SET(CMAKE_C_FLAGS "-g -O0 -fprofile-arcs -ftest-coverage -fprofile-instr-generate -fcoverage-mapping")
set(CMAKE_CXX_COMPILER clang++)
set(CMAKE_C_COMPILER clang)
set(CMAKE_CXX_STANDARD 14)


add_executable(${PROJECT_NAME}
  test.cpp
  main.cpp
  )
  
target_link_libraries(${PROJECT_NAME}
  gtest.lib
  gtest_main.lib
  gmock.lib
  gmock_main.lib
  ${GTEST_MAIN_LIBRARIES}
)

#add_custom_command(TARGET ${PROJECT_NAME} POST_BUILD
#    COMMAND ${PROJECT_NAME}
#    COMMENT "Running CRC32 check..."
#)