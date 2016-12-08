# =============================================================================
# Copyright (c) 2016 Raspberry Pi (Trading) Ltd.
# All rights reserved.
#
# FILE DESCRIPTION
# CMake build file for dtoverlay library.
# =============================================================================

cmake_minimum_required (VERSION 2.8)

project(libdtovl)

if (CMAKE_COMPILER_IS_GNUCC)
   add_definitions (-ffunction-sections)
endif ()

add_library (dtovl SHARED dtovl.c)

include_directories(${CMAKE_SYSROOT}/include)

target_link_libraries(dtovl fdt)

install (TARGETS dtovl DESTINATION lib)
install(FILES libdtovl.h DESTINATION include)
