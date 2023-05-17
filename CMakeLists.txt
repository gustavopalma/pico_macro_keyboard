cmake_minimum_required(VERSION 3.12)

# Pull in SDK (must be before project)
include(pico_sdk_import.cmake)

project(univ_arcade C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialize the SDK
pico_sdk_init()

add_executable(pico_keyb src/main.c src/usb_descriptors.c)

target_link_libraries(pico_keyb PRIVATE pico_stdlib tinyusb_device tinyusb_board)
target_include_directories(pico_keyb PRIVATE src/)

pico_add_extra_outputs(pico_keyb)