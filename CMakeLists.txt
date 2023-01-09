cmake_minimum_required(VERSION 3.14.0)

project(Figlet VERSION 2.2.5 LANGUAGES "C")

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED on)

set(FigletSrc "${PROJECT_SOURCE_DIR}/crc.c" "${PROJECT_SOURCE_DIR}/figlet.c" "${PROJECT_SOURCE_DIR}/getopt.c" "${PROJECT_SOURCE_DIR}/inflate.c" "${PROJECT_SOURCE_DIR}/utf8.c" "${PROJECT_SOURCE_DIR}/zipio.c")

if(MSVC)
    add_definitions("-D_CRT_SECURE_NO_WARNINGS=1")
endif()

add_executable(${PROJECT_NAME} ${FigletSrc})