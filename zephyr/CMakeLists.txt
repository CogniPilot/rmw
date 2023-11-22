# SPDX-License-Identifier: Apache-2.0
if (CONFIG_RMW)

zephyr_library_named(rmw)

target_compile_definitions(rmw PUBLIC
  )
target_compile_options(rmw PRIVATE -Wno-unused-variable -Wno-implicit-function-declaration -Wno-int-conversion)

zephyr_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rmw/include
  )

zephyr_library_include_directories(
  ${ZEPHYR_CURRENT_MODULE_DIR}/rmw/include
  )

file(GLOB_RECURSE Sources
  "${ZEPHYR_CURRENT_MODULE_DIR}/rmw/src/*.c"
)

#message(STATUS "Sources: ${Sources}")

zephyr_library_sources(
  ${Sources}
)

endif()
