# BME280 Driver [![Build Status](https://github.com/adafruit/Adafruit_BME280_Library/workflows/Arduino%20Library%20CI/badge.svg)](https://github.com/adafruit/Adafruit_BME280_Library/actions)[![Documentation](https://github.com/adafruit/ci-arduino/blob/master/assets/doxygen_badge.svg)](http://adafruit.github.io/Adafruit_BME280_Library/html/index.html)


<a href="http://www.adafruit.com/products/2652"><img src="./assets/board.jpg" width="500"/></a>

This is a driver for the BME280 Humidity, Barometric Pressure + Temp sensor

Designed originally to work with the Adafruit BME280 Breakout (but works with many other variants)
 * http://www.adafruit.com/products/2652

Adafruit invests time and resources providing this open source code, please support Adafruit and open-source hardware by purchasing products from Adafruit!

Modified by John Greenwell to adapt driver for custom HAL support, 2025.

## Usage

For this modified version, the following hardware abstraction layer (HAL) requirements must be satisfied:

* A header file `hal.h` providing access to HAL classes and methods.
* An `I2C` class within the `HAL` namespace with the following methods:
  - Write n bytes to the device: `uint8_t I2C::write(uint8_t addr, uint8_t * data, uint32_t len)`
  - Write n bytes to the device, execute a repeated start, then read n bytes from the device: `uint8_t I2C::writeRead(uint8_t addr, uint8_t * wr_data, uint32_t wr_len, uint8_t * r_data, uint32_t r_len)`
* A function in the `HAL` namespace that delays execution for n milliseconds: `void delay_ms(uint32_t time_ms)`
* A function in the `HAL` namespace that returns milliseconds elapsed during runtime (compare to well-known Arduino function of the same name): `uint32_t millis()`

Some further requirements may also be found. Typically, these will mirror the Arduino framework and should be added to `hal.h`.

# Installation
To install, use the Arduino Library Manager and search for "Adafruit BME280" and install the library.

## Dependencies
 * [Adafruit Unified Sensor Driver](https://github.com/adafruit/Adafruit_Sensor)

# Contributing

Contributions are welcome! Please read our [Code of Conduct](https://github.com/adafruit/Adafruit_PM25AQI/blob/master/CODE_OF_CONDUCT.md>)
before contributing to help this project stay welcoming.

## Documentation and doxygen
Documentation is produced by doxygen. Contributions should include documentation for any new code added.

Some examples of how to use doxygen can be found in these guide pages:

https://learn.adafruit.com/the-well-automated-arduino-library/doxygen

https://learn.adafruit.com/the-well-automated-arduino-library/doxygen-tips

## Formatting and clang-format
This library uses [`clang-format`](https://releases.llvm.org/download.html) to standardize the formatting of `.cpp` and `.h` files.
Contributions should be formatted using `clang-format`:

The `-i` flag will make the changes to the file.
```bash
clang-format -i *.cpp *.h
```
If you prefer to make the changes yourself, running `clang-format` without the `-i` flag will print out a formatted version of the file. You can save this to a file and diff it against the original to see the changes.

Note that the formatting output by `clang-format` is what the automated formatting checker will expect. Any diffs from this formatting will result in a failed build until they are addressed. Using the `-i` flag is highly recommended.

### clang-format resources
  * [Binary builds and source available on the LLVM downloads page](https://releases.llvm.org/download.html)
  * [Documentation and IDE integration](https://clang.llvm.org/docs/ClangFormat.html)

## About this Driver
Written by Ladyada for Adafruit Industries.

BSD license, check license.txt for more information

All text above must be included in any redistribution
