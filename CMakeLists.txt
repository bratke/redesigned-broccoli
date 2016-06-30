cmake_minimum_required(VERSION 2.8.4)
project(async_examples)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DAS_USE_LIBEV")

include_directories("./utils/src/include")

#set(SOURCE_FILES
#        async_examples/async_get/src/main/example.c
#        utils/src/main/example_utils.c)

set(SOURCE_FILES
        async_examples/async_tutorial.c)

add_executable(async_examples ${SOURCE_FILES})

target_link_libraries(async_examples aerospike)
target_link_libraries(async_examples crypto)
target_link_libraries(async_examples dl)
target_link_libraries(async_examples ev)
target_link_libraries(async_examples pthread)
target_link_libraries(async_examples rt)
target_link_libraries(async_examples z)
