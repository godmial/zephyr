# Pull Request Description

## Title
boards: Add esp32c3_lckfb board support and QMI8658C sensor driver

## Summary

This PR adds support for the LCKFB ESP32-C3 development board (esp32c3_lckfb) and implements a sensor driver for the QMI8658C 6-axis IMU sensor.

## Changes

### Board Support
- Added complete BSP support for esp32c3_lckfb board
  - Board configuration files (Kconfig, board.cmake, board.yml)
  - Device tree files (DTS, pinctrl)
  - Board documentation
  - OpenOCD debugging configuration
- Fixed BSP configuration to use generic ESP32-C3 SOC selection
- Updated vendor identifier to follow Zephyr convention (espressif)

### Sensor Driver
- Implemented QMI8658C 6-axis IMU sensor driver
  - Supports 3-axis accelerometer (±4g range)
  - Supports 3-axis gyroscope (±512dps range)
  - I2C interface support (address 0x6A)
  - Device tree bindings
- Added sample application demonstrating sensor usage
  - Polling mode operation at 10 Hz
  - Displays acceleration, angular velocity, and calculated tilt angles
  - Includes board-specific overlay for esp32c3_lckfb

## Testing

- Board BSP tested with QMI8658C sensor sample
- Sensor driver verified with sample application on esp32c3_lckfb board
- Build and flash operations successful

## References

- LCKFB ESP32-C3 Development Board: https://wiki.lckfb.com/zh-hans/szpi-esp32c3/
- QSTCORP QMI8658C datasheet
