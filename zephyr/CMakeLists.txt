cmake_minimum_required(VERSION 3.13.1)
# Find Zephyr. This also loads Zephyr's build system.
#find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
include($ENV{ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)
project(zephyr-webserver-test)

# Add your source file to the "app" target. This must come after
# find_package(Zephyr) which defines the target.
FILE(GLOB app_sources ../src/*.c*)
target_sources(app PRIVATE ${app_sources})

zephyr_include_directories(../include)

set(gen_dir ${ZEPHYR_BINARY_DIR}/include/generated/)

# generate_inc_file_for_target(app
# )