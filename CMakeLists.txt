cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/GolubkovArtem/hunter/archive/v0.19.137.1.tar.gz"
    SHA1 "6f15d4d1600e7ad9ab5b78db20c3394d40b63d0f"
)
project(lab12)

hunter_add_package(CURL)
find_package(CURL CONFIG REQUIRED)

set(SOURCE_FILES cget.cpp)
add_executable(lab12 ${SOURCE_FILES})

target_link_libraries(lab12 CURL::libcurl)
install(TARGETS lab12 RUNTIME DESTINATION bin)