cmake_minimum_required(VERSION 3.0)

project(homepage2ctrlq)

add_executable(homepage2ctrlq homepage2ctrlq.c)
target_compile_options(homepage2ctrlq PRIVATE -Wall -Wextra)

install(TARGETS homepage2ctrlq RUNTIME DESTINATION bin)
