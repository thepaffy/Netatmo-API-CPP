cmake_minimum_required(VERSION 3.5.0)

project(NAApiClientTest)
find_package(nlohmann_json)

include_directories(${CMAKE_CURRENT_BINARY_DIR})
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/../../../src)

file(GLOB NAApiClientTest_SRCS
    main.cpp
)

add_executable(${PROJECT_NAME} ${NAApiClientTest_SRCS})

target_link_libraries(${PROJECT_NAME}
    netatmoapi++
    gtest
)
add_test(NAApiClientTest NAApiClientTest)
