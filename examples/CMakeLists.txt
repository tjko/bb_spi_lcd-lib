cmake_minimum_required(VERSION 3.13)

include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)

project(spi_lcd_demo
  VERSION 1.0.0
  LANGUAGES C CXX ASM
  )
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_subdirectory(.. bb_spi_lcd-lib)

add_executable(spi_lcd_demo)

target_sources(spi_lcd_demo PRIVATE
	spi_lcd_demo.c
	)

target_link_libraries(spi_lcd_demo pico_stdlib pico_stdio_uart hardware_pio hardware_spi hardware_dma bb_spi_lcd-lib)

#enable serial output through usb
pico_enable_stdio_usb(spi_lcd_demo 1)
pico_enable_stdio_uart(spi_lcd_demo 0)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(spi_lcd_demo)

