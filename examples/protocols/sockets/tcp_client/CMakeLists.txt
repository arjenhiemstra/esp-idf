# The following lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.16)

if("${IDF_TARGET}" STREQUAL "linux")
    set(EXTRA_COMPONENT_DIRS "$ENV{IDF_PATH}/tools/mocks/freertos/"
                    "$ENV{IDF_PATH}/examples/protocols/linux_stubs/esp_stubs")
    set(COMPONENTS main)
    include($ENV{IDF_PATH}/tools/cmake/project.cmake)
else()
    set(EXTRA_COMPONENT_DIRS $ENV{IDF_PATH}/examples/common_components/protocol_examples_common)
    include($ENV{IDF_PATH}/tools/cmake/project.cmake)
endif()

project(tcp_client)
