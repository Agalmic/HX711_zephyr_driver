# SPDX-License-Identifier: Apache-2.0

zephyr_library()
zephyr_library_sources_ifdef(CONFIG_HX711 hx711.c)

if(CONFIG_HX711 AND (CONFIG_HX711_ENABLE_MEDIAN_FILTER OR CONFIG_HX711_ENABLE_EMA_FILTER))
  add_subdirectory(filters)
endif()