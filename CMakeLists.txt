cmake_minimum_required(VERSION 3.0)
project(LinkPython)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)

include(modules/link/AbletonLinkConfig.cmake)

add_subdirectory(modules/pybind11)

pybind11_add_module(link src/Link.cpp)

target_link_libraries(link PRIVATE Ableton::Link)
