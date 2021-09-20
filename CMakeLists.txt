
# ==========================================
#   Copyright (c) 2021 dynamic_static
#       Licensed under the MIT license
#     http://opensource.org/licenses/MIT
# ==========================================

cmake_minimum_required(VERSION 3.17 FATAL_ERROR)
project(dynamic_static.random)

################################################################################
# Dependencies
set(external "${CMAKE_CURRENT_LIST_DIR}/external/")
string(REPLACE "\\" "/" DYNAMIC_STATIC "$ENV{DYNAMIC_STATIC}")
include("${external}/dynamic_static.build.cmake")

################################################################################
# dynamic_static.random
dst_add_interface_library(
    target dynamic_static.random
    includeDirectories PUBLIC "${CMAKE_CURRENT_LIST_DIR}/include/"
    includeFiles "${CMAKE_CURRENT_LIST_DIR}/include/dynamic_static/random.hpp"
)

################################################################################
# dynamic_static.random.test
dst_add_target_test(
    target dynamic_static.random
    sourceFiles "${CMAKE_CURRENT_LIST_DIR}/tests/random.tests.cpp"
)
