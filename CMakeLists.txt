cmake_minimum_required(VERSION 3.13)
project(pwm CXX ASM)

set(CMAKE_CXX_STANDARD 17)

add_executable(pwm pwm.cpp)
target_link_libraries(pwm -lgpiodcxx)

add_executable(cpuburn-a7 ./cpuburn/cpuburn-a7.S)