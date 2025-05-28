cmake_minimum_required(VERSION 3.13)

# Convert PICO_SDK_PATH environment variable to native Windows style path if on Windows
if(WIN32)
    if(DEFINED ENV{PICO_SDK_PATH})
        file(TO_NATIVE_PATH "$ENV{PICO_SDK_PATH}" PICO_SDK_PATH_NATIVE)
        # Override the environment variable for the rest of this CMake run
        set(ENV{PICO_SDK_PATH} "${PICO_SDK_PATH_NATIVE}")
    endif()
endif()

project(blink_project C CXX ASM)

enable_language(ASM)

include($ENV{PICO_SDK_PATH}/pico_sdk_init.cmake)

pico_sdk_init()

add_executable(blink
    blink.c
)

target_link_libraries(blink pico_stdlib)

pico_add_extra_outputs(blink)
