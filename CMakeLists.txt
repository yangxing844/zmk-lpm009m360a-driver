zephyr_library()

zephyr_library_sources_ifdef(CONFIG_LPM009M360A src/lpm009m360a.c)
zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)
