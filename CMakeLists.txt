add_library(bb_spi_lcd-lib INTERFACE)
target_include_directories(bb_spi_lcd-lib INTERFACE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(bb_spi_lcd-lib INTERFACE pico_stdlib hardware_spi hardware_dma)
target_sources(bb_spi_lcd-lib INTERFACE
  ${CMAKE_CURRENT_LIST_DIR}/bb_spi_lcd.c
  ${CMAKE_CURRENT_LIST_DIR}/bb_spi_lcd.h
  ${CMAKE_CURRENT_LIST_DIR}/gif.c
  ${CMAKE_CURRENT_LIST_DIR}/AnimatedGIF.h
  )

