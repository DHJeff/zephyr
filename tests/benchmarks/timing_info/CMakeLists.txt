cmake_minimum_required(VERSION 3.8.2)
include($ENV{ZEPHYR_BASE}/cmake/app/boilerplate.cmake NO_POLICY_SCOPE)
project(timing_info)

FILE(GLOB app_sources src/[^u]*.c)
target_sources(app PRIVATE ${app_sources})
target_sources_ifdef(CONFIG_USERSPACE app PRIVATE src/userspace_bench.c)
