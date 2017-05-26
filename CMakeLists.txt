cmake_minimum_required(VERSION 3.8)

add_subdirectory(src)

option (TWM_BUILD_EXAMPLE "Build example" ON)

if (TWM_BUILD_EXAMPLE)
    add_subdirectory(example)
endif()