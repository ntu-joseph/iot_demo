# NOTE: This file is generated by yotta: changes will be overwritten!


project(mbed-trace)


# include root directories of all components we depend on (directly and
# indirectly, including ourself)
include_directories("/root/iot_demo/mbed-client-pi/mbed-linux")
include_directories("/root/iot_demo/mbed-client-pi/mbed-linux/yotta_modules/mbed-trace")
include_directories("/root/iot_demo/mbed-client-pi/mbed-linux/yotta_modules/nanostack-libservice")


# recurse into dependencies that aren't built elsewhere



# And others (typically CMSIS implementations) need to export non-system header
# files. Please don't use this facility. Please. It's much, much better to fix
# implementations that import these headers to import them using the full path.
include_directories("/root/iot_demo/mbed-client-pi/mbed-linux/yotta_modules/nanostack-libservice/mbed-client-libservice")


# modules with custom CMake build systems may append to the
# YOTTA_GLOBAL_INCLUDE_DIRS property to add compile-time-determined include
# directories:
get_property(GLOBAL_INCLUDE_DIRS GLOBAL PROPERTY YOTTA_GLOBAL_INCLUDE_DIRS)
include_directories(${GLOBAL_INCLUDE_DIRS})

# Provide versions of all the components we depend on, the corresponding
# preprocessor definitions are generated in yotta_config.h
set(YOTTA_MBED_TRACE_VERSION_STRING "1.2.1")
set(YOTTA_MBED_TRACE_VERSION_MAJOR 1)
set(YOTTA_MBED_TRACE_VERSION_MINOR 2)
set(YOTTA_MBED_TRACE_VERSION_PATCH 1)

# provide the name of the current module so that it's available to custom CMake
# even if custom CMake does weird things with project()
set(YOTTA_MODULE_NAME mbed-trace)

# recurse into subdirectories for this component, using the two-argument
# add_subdirectory because the directories referred to here exist in the source
# tree, not the working directory
add_subdirectory(
    "/root/iot_demo/mbed-client-pi/mbed-linux/yotta_modules/mbed-trace/source"
    "${CMAKE_BINARY_DIR}/ym/mbed-trace/source"
)

# make YOTTA_MODULE_NAME available as a preprocessor symbol when
# compiling this module:
target_compile_definitions(mbed-trace PRIVATE "-DYOTTA_MODULE_NAME=mbed-trace")

# include .cmake files provided by the target:
