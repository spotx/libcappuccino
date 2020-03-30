cmake_minimum_required(VERSION 2.8)
project(libcappuccino_test)

set(SOURCE_FILES_LIB_CAPPUCCINO_TEST
    CatchMain.cpp
    UnitTestTlruCache.cpp
    UnitTestUtlruCache.cpp
)

enable_testing()
add_executable(${PROJECT_NAME} ${SOURCE_FILES_LIB_CAPPUCCINO_TEST})
target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_17)
target_link_libraries(${PROJECT_NAME} PRIVATE 
    cappuccino
    catch # this is still spotx dependent!
    pthread
)

add_test(LibCappuccinoTest ${EXECUTABLE_OUTPUT_PATH}${PROJECT_NAME})
