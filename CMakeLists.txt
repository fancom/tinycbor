cmake_minimum_required(VERSION 3.13.1)
project(tinycbor)

set(TARGET tinycbor)

set(SOURCE_PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/src)
set(INCLUDE_PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/src)

set(HEADERS
    ${INCLUDE_PREFIX}/cbor.h
    ${INCLUDE_PREFIX}/tinycbor-version.h)

set(SOURCES
    ${SOURCE_PREFIX}/cborencoder_close_container_checked.c
    ${SOURCE_PREFIX}/cborencoder.c
    ${SOURCE_PREFIX}/cborerrorstrings.c
    ${SOURCE_PREFIX}/cborparser_dup_string.c
    ${SOURCE_PREFIX}/cborparser.c
    ${SOURCE_PREFIX}/cborparser_dup_string.c)

add_library(${TARGET} STATIC ${SOURCES} ${HEADERS})

install(FILES ${HEADERS} DESTINATION include/tinycbor)
