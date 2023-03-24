cmake_minimum_required(VERSION 3.13)

set(PICO_BOARD pico_w)

# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake)
include(pico_extras_import_optional.cmake)

project(blink)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

add_executable(blink
    blink.c
    )

target_link_libraries(blink
    pico_stdlib              # for core functionality
    pico_cyw43_arch_none     # we need Wifi to access the GPIO, but we don't need anything else
    )

pico_add_extra_outputs(blink)

