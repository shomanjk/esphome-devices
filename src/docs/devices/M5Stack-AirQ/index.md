---
title: M5Stack AirQ
date-published: 2025-01-08
type: sensor
standard: global
board: esp32
difficulty: 2
---

## Product Images

![M5Stack AirQ](M5stack-AirQsensorDisplay.jpeg "M5Stack AirQ ESPHome screen")
![M5Stack AirQ](M5stack-AirQ.webp "M5Stack AirQ product details")

## Description

M5Stack AirQ is an integrated air quality monitor built around the M5Stack StampS3 controller, Sensirion SEN55 air
quality sensor, Sensirion SCD40 CO2 sensor, and a 1.54-inch 200x200 e-ink display. It monitors PM1.0, PM2.5, PM4,
PM10, VOC, NOx, CO2, temperature, and humidity.

The example below is a hardware-first ESPHome configuration for the onboard sensors, display, buttons, RGB LED, SEN55
power switch, battery HOLD latch, and battery-voltage ADC. It intentionally leaves out API, OTA, web server, and Wi-Fi
credentials so those can be added in the user's own local configuration.

This YAML was originally adapted from a sample provided by **joshblake87** at
[https://www.reddit.com/r/Esphome/comments/1e2q8jj/m5_stack_airq_air_quality_sensor/](https://www.reddit.com/r/Esphome/comments/1e2q8jj/m5_stack_airq_air_quality_sensor/).

## Battery Notes

The AirQ uses GPIO46 to keep battery power latched. This configuration turns that latch on early during boot and reads
pack voltage on GPIO14 through the onboard divider. Automatic low-voltage shutdown is disabled by default
(`battery_shutdown_voltage: "0"`); set it to an under-load threshold such as `3.30` only after verifying your unit's
battery-voltage readings.

## GPIO Pinout

| Pin    | Function           |
| ------ | ------------------ |
| GPIO0  | Button A / download mode |
| GPIO1  | Ink Screen Busy    |
| GPIO2  | Ink Screen RST     |
| GPIO3  | Ink Screen D/C     |
| GPIO4  | Ink Screen CS      |
| GPIO5  | Ink Screen SCK     |
| GPIO6  | Ink Screen MOSI    |
| GPIO8  | Button B           |
| GPIO9  | Beep               |
| GPIO10 | SEN55 Power Switch |
| GPIO11 | I2C SDA            |
| GPIO12 | I2C SCL            |
| GPIO13 | GROVE A SDA        |
| GPIO14 | Battery Voltage ADC |
| GPIO15 | GROVE A SCL        |
| GPIO21 | RGB LED            |
| GPIO26 | Speaker Pin 2      |
| GPIO42 | Power Button       |
| GPIO46 | Battery HOLD latch |

## Example Configuration

```yaml file=config.yaml
```
