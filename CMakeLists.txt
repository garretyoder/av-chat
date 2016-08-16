cmake_minimum_required(VERSION 3.5)
project(avchat)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -lboost_system")

set(SOURCE_FILES main.cpp)
add_executable(avchat ${SOURCE_FILES})

set(Boost_USE_STATIC_LIBS        ON)
set(Boost_USE_MULTITHREADED      ON)
set(Boost_USE_STATIC_RUNTIME    OFF)
find_package(Boost 1.6.0 COMPONENTS asio)
if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(avhat avchat.cpp)
    target_link_libraries(avchat ${Boost_LIBRARIES})
endif()