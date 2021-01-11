cmake_minimum_required(VERSION 3.0)

project(ralt2hyper)

add_executable(ralt2hyper ralt2hyper.c)
target_compile_options(ralt2hyper PRIVATE -Wall -Wextra)

install(TARGETS ralt2hyper RUNTIME DESTINATION bin)
